讓 Synology Nas 開啟 Https 時不再跳出憑證錯誤（以 StartSSL 為解決方案）
====

因為網路的普及，所以 NAS 在居家生活似乎也越來越常見，但我們總是希望自己的資料在網路傳輸時可以安全一點而非在裸奔，所以大家都會選擇開啟 Https 來保護資料的傳輸，但大家是否有發現到，預設所使用的憑證是廠商自己簽的，所以使用 Chrome 或是 Firefox 時會跳出安全警示很麻煩？

[什麼是 Https ? 請參考維基百科](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%AE%89%E5%85%A8%E5%8D%8F%E8%AE%AE)

憑證是自簽或是有錯誤的時候，紅紅的感覺很恐怖
![](https://photo.hy31.net/2015/SSL/2/1.png)


經過可信任第三方簽署過的憑證，就是一個綠色的鎖頭
![](https://photo.hy31.net/2015/SSL/2/2.png)


##憑證自簽與透過第三方信任單位簽署之差異

*	正常來說，所有的 Https 服務應該都要有被第三方信任單位簽署 SSL 憑證，這樣才能確保你所連接的是真的服務，而非是假冒的
*	雖然自簽的 SSL 憑證也是會讓流量加密，但是當遇到中間人或是類似的攻擊的時候，相較於有第三方信任單位簽署 SSL 的只要發現憑證有誤就可能是流量遭到攻擊，但自簽憑證因為本來就會報錯，所以需要自行比對 MD5 或是 SHA 值才能知道是否有被更換過憑證
*	在部分新版瀏覽器中，自簽憑證的服務預設是被封鎖的，所以容易造曾使遇上的不便

所以拉，如果有免費的 SSL 憑證可以申請，為什麼不申請呢？


##申請免費 SSL 的優與劣

*	優：免費、可以不再讓憑證報錯
* 	劣：皆為 Class1 等級，第三方只做低限度的驗證，並不適合商業或是金流等需要高度安全與身份驗證的服務使用，且部分舊版瀏覽器可能不信任 Class 1 等級的憑證



##教學（以 StartSSL為例）

*	申請 StartSSL 帳號方式請參考過去文章

1. 登入後請選左上方的 Validations Wizard 後在 Type 選擇 Domain Name Validation
![](https://photo.hy31.net/2015/SSL/3/1.png)
![](https://photo.hy31.net/2015/SSL/3/2.png)
![](https://photo.hy31.net/2015/SSL/3/3.png)




2. 接著輸入你的網域，然後選擇要來驗證的Email就可以該信箱收驗證信並回填，然後就會看到驗證成功的訊息
![](https://photo.hy31.net/2015/SSL/3/4.png)
![](https://photo.hy31.net/2015/SSL/3/5.png)

3. 接著就是回到主畫面然後再次點選上方的 Certificates Wizard ，然後在 Certificate Target 中選擇 Web Server SSL/TLS Certificate ，在按下 Continue 選擇 Key 的加密等級、演算法與密碼
而這邊是建議長度可以選擇 4096 而演算法要選擇 SHA2 
![](https://photo.hy31.net/2015/SSL/3/6.png)
![](https://photo.hy31.net/2015/SSL/3/7.png)


4. 這一步會產生出私鑰來，請務必保管好，然後千萬要注意要用 ASCII 編碼存檔，不可以用 UTF-8 ，然後檔案附檔名記得存成 .key 並好好保管，因為這就是你的私鑰
![](https://photo.hy31.net/2015/SSL/3/8.png)
![](https://photo.hy31.net/2015/SSL/3/9.png)

5. 接下來就是選擇你要簽的網址是什麼，然後輸入後他會需時間人工審核，所以就是等 Email 通知，通常是一天內就會審核通過
![](https://photo.hy31.net/2015/SSL/3/10.png)



6. 當審核通過後一樣回到主選單選擇 Tool Box 中的 Retrieve Certificate，並且選擇你的憑證網域，然後把整個文字複製下來存成附檔名為 .crt 的檔案，且注意編碼需要為 ASCII 
![](https://photo.hy31.net/2015/SSL/3/11.png)
![](https://photo.hy31.net/2015/SSL/3/12.png)
![](https://photo.hy31.net/2015/SSL/3/13.png)




7. 因為我們剛剛產生的私鑰有加密，但是 Synology Nas所匯入的只能用未加密的私鑰，因此一樣再次打開 Tool Box 並且選擇 Decrypt Private Key ，然後一樣把原本 .key檔裡面的資訊與密碼輸入進去，就會獲得解碼過的私鑰，然後一樣把他存成 .key 檔，並且好好好管，這邊還是要一樣要注意編碼是ASCII
![](https://photo.hy31.net/2015/SSL/3/14.png)
![](https://photo.hy31.net/2015/SSL/3/15.png)




8. 現在理論上你會有三個檔案，憑證檔 .crt 、加密的 .key 、 已解密的 .key ，然後這時候就可以打開你的 Synology 管理頁面，選擇 控制台 -> 安全性 -> 憑證 -> 匯入憑證，然後把已解密的 .key 與 憑證 .cet上傳上去，就完成了
![](https://photo.hy31.net/2015/SSL/3/16.png)
![](https://photo.hy31.net/2015/SSL/3/17.png)
![](https://photo.hy31.net/2015/SSL/3/18.png)






最後只要把瀏覽器重開就可以看到是顯示綠色鎖頭的憑證了 :0
![](https://photo.hy31.net/2015/SSL/2/2.png)














