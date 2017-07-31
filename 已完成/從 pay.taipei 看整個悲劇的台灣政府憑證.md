從 pay.taipei 看整個悲劇的台灣政府憑證
====

昨天最夯的科技新聞莫過於台北市政府官方的支付平台 pay.taipei 上線後被 [Gandi 亞太區總經理](https://www.facebook.com/schreibmal/media_set?set=a.10212928669916690.1073741842.1388906446&type=3&pnref=story)爆出連線是走 http + IP，這根本是裸奔＋自殺的行為。


原本以為是工程師無腦的忘記在測試環境轉正式環境時加上安全性，但現在看起來其實背後可能是有更大問題的。

### 可能原因

在昨天還沒上新聞前 pay.taipei 是用 GRCA2 的憑證，就如同其他像是 auth.taipei 一樣。但 pay.taipei 被罵後卻立刻換成 Let's encrypt，我想這就是當時麼便宜行事用 HTTP 的原因。因為 pay.taipei 有很大一部份是行動用戶，而台灣 Adnroid 手機又佔了大宗。

但是 GRCA2 的憑證目前還沒有進入到 Android 手機的內建憑證庫內，所以如果如果使用 https 就會跳出警示錯誤，因為系統根本不信任這憑證（當然我覺得因此就用 http 連線更蠢）。

然後 Android 團隊決定是否收這憑證進入內建憑證庫的原則就是看主流機構都收了他就收，可是 GRCA2 憑證與 GRCA 憑證同名不同金鑰，所以被 Mozilla 認為有風險一直處理到最近才勉為其難的放行（這一拖就是三年多了）。

bugzilla 討論串： [https://bugzilla.mozilla.org/show_bug.cgi?id=1065896](https://bugzilla.mozilla.org/show_bug.cgi?id=1065896)

Google Group 討論串： [https://groups.google.com/forum/#!msg/mozilla.dev.security.policy/eFG27ZTYWD8/YFkZ7cdIBQAJ](https://groups.google.com/forum/#!msg/mozilla.dev.security.policy/eFG27ZTYWD8/YFkZ7cdIBQAJ)

所以理論上之後 Adnroid 團隊就會把 GRCA2 憑證放入系統內建了吧（？）


### 爭議點

到底政府簽發的憑證有沒有一定要讓主流系統信任的過，這到底始終沒有一個好的共識。但就現實來說，之前可以看到很多政府單位的教學都是請使用者自行安裝憑證進去來讓系統信任。雖然這已經比過去一些單位要求使用者降版或是關掉安全性、更新的方式來的好很多。但這對使用者終究造成不方便 Orz


### 讓我們看下去

就目前 pay.taipei 改用 Let's encrypt 至少讓 Android 手機已經可以正常連線了，但是到底它們會記得在三個月後記得更新嗎（？）

此外就我自己的認知，金流等級的 App 應該需要有做 certificate pinning，當然用 Let's encrypt 也是可以做拉，但你每三個月就一定要使用者更新 App 應該會被抱怨到極致吧，花點錢買付費憑證應該不難吧。

而且目前看到新聞說它會關閉 http 的驗證方式，但也請做個 301 導向到 https 不要直接讓使用者無法連線，並不是每一個使用者都會知道要在網址加上 https:// 才可以正常連線。


對了，目前 Android 使用者如果使用網頁版還是會悲劇，因為 pay.taipei 登入時會轉跳 auth.taipei 做登入驗證，但 auth.taipei 還是用 GRCA2。

