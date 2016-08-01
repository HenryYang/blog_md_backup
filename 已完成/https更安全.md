[筆記] 調整 HTTPS 的設定讓網站更安全一點 for Apache
====


有太多服務年久失修了，所以只好一步一部來處理，這次先把服務修到 A＋ 但沒有修到滿分，因為要到滿分很多東西都需要重新編譯，然後我這台主機又異常老舊，這次先解決嚴重的安全問題，以下就只是處理時紀錄下來的相關資訊


### 開啟 Forward Security、關閉舊協定（Protocol）、關閉不安全的密碼套件（CipherSuite）

這邊的修改都是改你的 Apache 設定檔

```{r, engine='bash', count_lines}
SSLProtocol -ALL -SSLv3 +TLSv1 +TLSv1.1 +TLSv1.2
#正面列表，只允許有列出的 TLS 協定可以使用

SSLHonorCipherOrder on
SSLCipherSuite AES256+EECDH:AES256+EDH:AES128+EECDH:AES128+EDH
#正面列表，只使用最新的橢圓加密
```


### 開啟 HSTS

註，最低版本需要 Apache 2.2.22

首先先用 a2enmod 開啟 headers 這模組

```{r, engine='bash', count_lines}
sudo a2enmod headers
```

然後同樣的修改你的 Apache 設定檔，加上以下這指令，而這邊設定的時間是一年

```{r, engine='bash', count_lines}
Header always set Strict-Transport-Security "max-age=31536000;includeSubdomains; preload"
```


### 解決 Diffie-Hellman 公開金鑰不足問題

註，最低版本需要 Apache 2.4.8 (含)以上與 OpenSSL 1.0.2d (含)以上之版本

透過 Openssl 產生憑證，這邊可能會花你半小時的時間，可以按下 Enter 後去好好休息

```{r, engine='bash', count_lines}
openssl dhparam -out /etc/ssl/private/dhparams_4096.pem 4096
```

然後同樣的修改你的 Apache 設定檔，加上以下這指令

```{r, engine='bash', count_lines}
SSLOpenSSLConfCmd DHParameters "/etc/ssl/private/dhparams_4096.pem"
```



##結論

要記得如果每個步驟做完如果就想立刻看結果要把 Apache 服務重起，然後千萬記得不要再讓自己的服務在裸奔拉～



###參考連結：
https://itigloo.com/security/how-to-configure-http-strict-transport-security-hsts-on-apache-nginx/
https://community.letsencrypt.org/t/howto-a-with-all-100-s-on-ssl-labs-test-using-apache2-4-read-warnings/2436
http://www.arthurtoday.com/2011/11/ubuntu-apache-ssl-self-signed.html
http://netkiller.sourceforge.net/cryptography/openssl/format.html
http://masnec.logdown.com/posts/184740-ssl-certificate
http://csc.ocean-pioneer.com/docum/ssl_basic.html
http://blog.miniasp.com/post/2012/06/23/apache2-Could-not-reliably-determine-the-server-fully-qualified-domain-name-using-for-ServerName.aspx
http://www.arthurtoday.com/2015/02/ubuntu-command-line-reconfig-time-zone.html