用 YubiKey 登入遠端主機吧！！！
=====




###[如果不知道什麼是 YbuiKey 的人可以先看看這篇文章喔]()


說到登入遠端主機，大家想到的應該就是圖形化代表 Windows 的遠端桌面（RDP）跟 VNC ，而 *NIX 系統常用的 CLI 登入就屬 SSH 莫屬了。

這邊要介紹的就是提供 SSH 登入有另一種更安全的登入方式，過去常見登入 SSH 都是透過密碼登入，這樣的好處是驗證方式就是密碼，只要密碼在腦袋內，除非系統要特殊限制，不然在任何一個地方都是可以連上主機的，但這也帶來另一個問題就是如果密碼不小心被有心人士知道，主機的安全也就會跟著淪陷。因此目前另外一種相對安全的方式就是透過公開金鑰認證的方式將公鑰與私鑰放在遠端與本地端做驗證，這樣就可以免去密碼驗證容易被暴力破解的風險。

但公開金鑰認證的缺點是如果放在本地端的私鑰檔案一旦被偷走，一樣會造成主機淪陷的風險。因此我這邊要介紹的就是利用 YubiKey 支援 OpenPGP Card 的這項優點，將驗證用的金鑰直接寫入 Yubikey 的硬體中，因為這是單向性的寫入，所以寫入後是無法在讀回電腦的，因此除非實體的 YubiKey 遺失，不然其他有心人士是無法冒充你登入遠端主機的。

##測試環境

客戶端： Mac OS X 10.11.4 、 GnuPG 2.0.30 、 GPGSuite 2016.07

伺服器端： Ubuntu 14.04

所需軟體： OS X 的使用者請去下載 [GPG Suite](https://gpgtools.org/)他會幫你把所有需要的裝好，而 Windows 的使用者則是推薦使用 [GPG4WiN](www.gpg4win.org/download.html) 然後連線軟體請使用 [Putty安裝版](https://the.earth.li/~sgtatham/putty/latest/x86/putty-0.67-installer.msi)

注意事項：如果是 OS X 10.10 (含)以後的使用者，請務必確認你的 GnuPG 版本至少是 2.0.29 以後，因為在那之前的版本會導致在 10.10 (含)以後系統中 PCSC library 不知名的原因會不定時當機，然後就辨識不到，我就是踩到這個雷，請務必注意到 Orz


##設定步驟

以下將會以 OS X 為主要操作畫面

產生公鑰與私鑰（圖形化還是文字介面都可以） -> 新增子鑰並設定其為 Authentication Key -> 修改 YubiKey 的模式 -> 把子鑰寫入 YubiKey -> 把子鑰轉換成 SSH public keys 格式並上傳到遠端主機

### Step1 產生公鑰與私鑰

首先當然是產生屬於自己的金鑰，因此如果是已經有金鑰的人可以直接略過本步驟。然後這步驟想用圖形介面還是文字都可以，主要就是產生出屬於自己的公鑰與私鑰即可，然後附圖是透過 GPG Suite 中的 GPG Keychain 產生。然後要記得的是如果你是 Neo 版本的 RSA 長度只能選到 2048 ，要 YubiKey 4 的才有支援到 RSA 4096 ，這請特別注意。

![](https://photo.hy31.net/2016/yubissh/0001.png)

產生完後應該會看到一組 Type 是寫 sec/pub 然後是你輸入的名字與 Email 的資料，這樣就代表你已經產生好自己的金鑰，然後記得在上面按右鍵 Export 匯出備份檔然後妥善收好（請記得要勾選下方的 Include secret key in exported file 這樣才會把私鑰一起備份）。

![](https://photo.hy31.net/2016/yubissh/002.png)


![](https://photo.hy31.net/2016/yubissh/003.png)



### Step2 新增子鑰並設定其為 Authentication Key

這部分因為圖形化介面簡化了很多選項，所以需要使用文字介面來達成，理論上只要安裝完成而且環境變數有設定好應該在終端機 （OS X）或是命令提示字元（Windows）輸入 gpg -help 就會看到 gpg 這程式的相關東西

![](https://photo.hy31.net/2016/yubissh/004.png)


\#顯示目前擁有的金鑰，理論上會看到類似下圖東西

gpg -K


![](https://photo.hy31.net/2016/yubissh/005.png)


\#理論上只有一組，然後如果有多組就請看名稱與 Email 來辨識，並記下八碼的16進位代碼，然後輸入以下指令來選擇要將哪一組金鑰來新增子鑰（請將最後那八碼換成你自己的）

gpg --expert --edit-key AAE904FF


![](https://photo.hy31.net/2016/yubissh/006.png)


\# 當出現類似上面的畫面後，就輸入 addkey 來新增子鑰，跳出的視窗是要求你輸入產生金鑰時你所設定的密碼，輸入完後應該就會看到選擇畫面。


![](https://photo.hy31.net/2016/yubissh/007.png)


\# 這邊請選擇第 8 號選項，然後他會跳出要你選擇子鑰類型，這邊可以看到他預設已經選了 Sign 跟 Encrypt，但我們需要的是 Authenticate ，所以就是輸入 A 按下 Enter來選取 Authenticate ，然後輸入 S 來取消選取 Sign 接著是輸入 E 來取消選取 Encrypt，最後就是按下 Q 來結束設定。

![](https://photo.hy31.net/2016/yubissh/008.png)

![](https://photo.hy31.net/2016/yubissh/009.png)


\# 接著系統會問加密模式與是否過期都直接 Enter 即可，然後皆下來兩個都按 Y ，這時系統就會跳出金鑰類型，請確認你最下面那組的 usage是否為 A，如果是就請輸入 save 來存檔。

![](https://photo.hy31.net/2016/yubissh/010.png)

![](https://photo.hy31.net/2016/yubissh/012.png)



### Step3 修改 YubiKey 的模式

狀況是說 YubiKey 支援很多模式，但不知道為什麼一開始 OpenPGP 所需要的 CCID 模式是關的，然後官網跟網路上的教學大多都是教下 -m82 這參數，但這會把 U2F 功能關掉，明明[官方文件](https://developers.yubico.com/libu2f-host/Mode_switch_YubiKey.html)就有提供 -m6 這全開的方法，然後不建議用 -m86 這參數的原因是他會變成需要每次切換都需要插拔才可以，有點麻煩...

\# 去官網下載[文字介面的 Yubico Personalization Tool ](https://www.yubico.com/support/downloads/)然後解壓縮後用終端機切到該目錄，然後執行以下指令然後在按下 y 就完成模式更改。

./ykpersonalize -m6

![](https://photo.hy31.net/2016/yubissh/013.png)



### Step4 把子鑰寫入 YubiKey

這時候一樣還是在文字介面使用 gpg 這工具。

\#首先先輸入以下指令來看看有沒有正確辨識到 YubiKey 的 OpenPGP Card，如果有出現類似下的就代表有成功開啟了

gpg --card-status 

![](https://photo.hy31.net/2016/yubissh/018.png)


\#輸入以下指令（後八碼還是輸入跟在 Step2 一樣的），然後再輸入 toggle 來開始選擇則子鑰，理論上剛剛產生的 Authentication key 會是第二個 ssb 所以就是輸入 key 2 這時候應該就會看到第二個 ssb 前面多了 * 號，這時候再輸入 keytocard 然後系統會跳出問你要把他當成哪一種，理論上就只會有 Authentication key 這一種，你就是輸入 3 ，這樣就完成了，你就可以再輸入 quit 離開 gpg 程式。 

gpg --edit-key AAE904FF

![](https://photo.hy31.net/2016/yubissh/014.png)


### Step5 把子鑰轉換成 SSH public keys 格式並上傳到遠端主機

請注意，不知道為什麼 Windows 平台沒有 gpgkey2ssh 這程式，你可以選擇裝 Cygwin 或是把金鑰匯到其他平台做轉檔。

\# 就找到你剛剛寫入的子鑰的後八碼，然後輸入以下指令（請把那八碼改成你自己的），然後顯示的東西就存放在你遠端主機使用者家目錄下 ./.ssh/authorized_keys 這檔案內（如果沒有就自己創）

gpgkey2ssh E9AC2F05

![](https://photo.hy31.net/2016/yubissh/015.png)

## 這樣就完成拉

這時候如果你照往常的輸入 ssh 使用者名稱@主機位置 理論上就會跳出 GPG Suite 要你輸入 YubiKey 的使用者密碼，記得不是你遠端主機的使用者密碼喔，這樣就可以免密碼，透過 YubiKey 中的 OpenPGP Card 登入了！

![](https://photo.hy31.net/2016/yubissh/017.png)


註： YubiKey 預設的使用者密碼是 123456 而管理者密碼是 12345678 ，如果要修改，請輸入 gpg --card-edit ，然後在輸入 admin 切入最高權限後輸入 passed 就可以修改了，記得一定要修改喔！

![](https://photo.hy31.net/2016/yubissh/016.png)


請注意，如果使用者密碼連續輸入錯 3 次會被鎖定，需要輸入管理員密碼解鎖，但如果連管理員密碼也輸入錯 3 次就這 Yubikey 就只能[整支重置](https://developers.yubico.com/ykneo-openpgp/ResetApplet.html)。



###參考資料：

https://www.yubico.com/2012/12/yubikey-neo-openpgp/
https://www.yubico.com/2012/12/yubikey-neo-composite-device/
https://developers.yubico.com/libu2f-host/Mode_switch_YubiKey.html
http://florin.myip.org/blog/easy-multifactor-authentication-ssh-using-yubikey-neo-tokens
https://developers.yubico.com/PGP/Importing_keys.html
https://www.jfry.me/articles/2015/gpg-smartcard/#osx
https://trmm.net/Yubikey
https://www.esev.com/blog/post/2015-01-pgp-ssh-key-on-yubikey-neo/





