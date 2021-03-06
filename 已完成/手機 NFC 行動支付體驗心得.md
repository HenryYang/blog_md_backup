手機 NFC 行動支付體驗心得
====

目前市面上行動支付主要可以分為 HCE (Host Card Emulation 主機板模擬) 、 TSM (Trusted Service Manager 信託服務管理) 這兩種技術，而目前最夯的 ApplePay 其實就是跟 HCE 一樣，背後都是使用 Tokenization 技術來完成。

因為 HCE 跟 ApplePay 都是每一次交易時獲取一次性使用的 Token 來做交易（其實 Token 格式就是跟傳統的信用卡格式一樣，只是每次交易都不一樣），而 TSM 則是將信用卡卡號存在安全元件（通常是 SIM 卡或是記憶卡中），所以交易每一次都是同一組卡號。

然後很巧的是我剛好我手邊有的使用 TSM 技術的 RicoPay 、 HCE 技術的玉山 Wallet 跟 Apple Pay ，所以以下就記錄一下各軟體開的操作步驟與所需時間。

### ApplePay
操作方式：
將手機靠近刷卡機或是開啟螢幕點擊 Home 鍵兩下以開啟 ApplePay → 選擇想要用的卡片 → 靠近刷卡機並按下指紋完成支付。

所需時間：4秒


### RicoPay
操作方式：
開啟螢幕並解鎖(如果有上密碼)後 → 開啟 RicoPay 軟體 → 輸入四位數密碼 → 選擇想要的卡片 → 點選螢幕上的支付按鈕並靠近刷卡機以完成支付。

所需時間：22秒



### 玉山 Wallet
操作方式：
開啟螢幕並解鎖(如果有上密碼)後 → 開啟玉山 Wallet 軟體 → 輸入八位數密碼 → 靠近刷卡機以完成支付。

所需時間：11秒



##使用心得與後記

以真實使用情境來說， ApplePay 是真的可以很幽雅的在結帳完後才從口袋拿出手機來支付，因為只要 4 秒，所以有時候會比從皮夾拿出感應信用卡還快。而 RicoPay 因為登入速度過慢，所以一定要在結帳時就把軟體登入好，不然如果在結帳後才開始上述步驟通常會被店員厭惡。然後另一點要注意的是如果你的 Andorid 手機有裝多套可以使用的 NFC 支付的軟體，可能會讓支付所需時間更久，因為系統一次只能選擇一種使用，所以每一次切換使用就會跳出詢問，所以行動支付真的是 Apple Pay 大勝。
然後你問我這類的行動支付會流行嗎？我覺得問題在於店家願不願意更新刷卡機會是推廣最大的阻力，因為在台灣可以刷信用卡的店家非常多，但是大約還有一半的商店是無法使用感應支付的，所以當越多的商店支援感應刷卡後，行動支付就會越來越盛行。
P.S. 理論上只要支援 Visa Wave 、 Master PayPass 、 JCB Jspeedy 任一種的感應刷卡機就都可以支援 NFC 行動支付，但有時候聯合信用卡處理中心的舊刷卡機就是會不明原因刷不過 :(
