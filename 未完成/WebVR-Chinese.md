-----
20171113
# [生活] 線上零售商 Target 運用 WebAR 讓消費者在家就能知道家具是否適合適

傳統購買大型家具最大問題總是只能透過想像去購物，而知名的 Target 則是在自家的 App 內導入 WebAR 技術，讓人可以快速的知道想要購買的物品是否符合自己真實的環境。

https://twitter.com/Goglasses/status/923512179097260032

https://www.goglasses.fr/realite-augmentee/target-webar-meuble

-----

# [教學] 快速上手的全雲端開發 WebVR 解決方案 - rodin

其實對於新手最大的問題一直都是環境設定、網站設定架設等等的雜碎問題，然後 rodin 是一套 Online IDE 環境的 WebVR 解決方案，所以今天使用者完全就只需要一個瀏覽器，就可以在瀏覽器中完成設定、撰寫程式碼、部屬與執行應用而不需要另外再安裝其他軟體。然後他也支援各家的頭帶式顯示器，所以如果是第一次想開發也是可以考慮看看這平台的。

https://medium.com/rodinvr/getting-started-with-rodin-io-3476a3bd3a25

https://rodin.io/

-----
# [外掛] WebVR API 模擬器 - WebVR API Emulation

當想開發 WebVR 相關的應用，但是又沒有專用的頭帶式顯示器時這時候 這一個 Chrome 的外掛套件則是非常好用的，因為它可以模擬出畫面與三軸空間來，讓開發者可以以最接近有實體設備的情況下開發，而目前這外掛可以模擬 HTC VIVE 的頭帶式顯示器的顯示效果。


https://github.com/spite/WebVR-Extension

https://chrome.google.com/webstore/detail/webvr-api-emulation/gbdnpaebafagioggnhkacnaaahpiefil

-----

# [新知] 音樂對 WebVR 帶來的改變

這篇文章主要提到的 WebVR 應用是在前幾週的報到中我們就已經有介紹過的 Inside Music 這超酷炫音樂 WebVR 專案。然後這篇文章的重點是他整了不少有趣有關音樂的 WebVR 應用，所以想以音樂為發想的人千萬不要錯過。之後我們也會挑幾個最有趣的在之後的期數介紹。


https://twitter.com/robclarke/status/926182165120987136

https://www.learningarchitects.com/how-music-is-made-with-exciting-technology-webvr/

https://experiments.withgoogle.com/webvr/inside-music/view/


-----
# [新知] Sketchfab 推出支援 WebVR 的 App 讓使用者能將各種模型以 VR 模式觀看

Sketchfab 是目前一個知名的 3D 模型分享平台，然後日前開始支援
Oculus、HTC Vive、Gear VR、Cardboard 來運行他們的 App 已使用 VR 模式觀看，這樣讓使用者能有更簡便的方法來觀賞與使用 Sketchfab 的資源。

https://www.archdaily.com/787666/sketchfab-adds-support-for-apps-and-webvr

https://sketchfab.com/

-----
# [新奇] 想看火星的真實樣貌嗎？現在 Google 與 NASA 合作的專案讓你一次看的夠。

這是一個由 NASA Jet Propulsion Laboratory 與 Google 合作的計畫，把真實的火星地貌移植到 360 度的互動 WebVR 上。讓每一個對火星有興趣的人，不像過去只能看照片還可以身歷其境的用 VR 來體驗。

https://twitter.com/DClark_Tweet/status/922277153760190464

-----


# [討論] 當混合實境走入 Web 的環境

> 今天 Mozilla 宣布一個新的開發計畫是要在 Web 中把混合實境整合擴展到虛擬實境與擴增實境中。我們最原始的目標是如何讓設備、頭盔、 WebVR 框架與相關的工具能運作的順暢。所以 Web 工程師就可以輕鬆的從熟悉的工具中做選擇並且創作與發佈身歷其境的應用。

這編算是 Mozilla 官方自己細數近期 WebVR 技術中重大的事項，然後也為了讓 VR 與 AR 的整合更加密切，所以目前也提出了 WebXR API 的草案，希望能讓未來開發 WebVR 與 WebAR 的門檻更低與用容易取用。



https://blog.mozilla.org/blog/2017/10/20/bringing-mixed-reality-web/


-----
20171023

# [規格] WebXR 草案 - 讓 WebVR 包含 AR/MR 的相容性

這目前還只是一份草案來討論 WebXR 的規格，但是它預計之後會擴充 WebVR 對於 AR/MR 的相容性，所以未來的應用是可以期待的，然後有興趣的人目前 WebXR 已經透過 polyfill 來運作的範例程式。

https://github.com/mozilla/webxr-api

-----
# [技術] Windows 10 冬季更新帶來更多 WebVR 體驗

> 早在今年 4 月我們就已經宣布這次的 Windows 10 更新中 Edge 會支援 WebVR 1.1 的 API， 以提供數以百計的開發者透過 Windows Mixed Reality 開發者套件來開發各種 VR 相關的使用。

今年的 10/17 號 EdgeHTML 16 跟著 Windows 10 Fall Creators Update 一起推出了，微軟目標以 Windows Mixed Reality 的支援裝置來達到高普及率與低門檻的特色，並且用此來推廣自家的 Microsoft Edge 瀏覽器。

而且當然也不意外的這次的 Windows Mixed Reality 平台支援了主流的 WebVR 框架，如： A-Frame, BabylonJS, ReactVR 與 three.js；而更重要的是目前也已經支援了動態感測的控制器了。

從處處我們都可以看到這一次微軟不論是平台還是硬體都有想進入到 WebVR 的決心，所以讓我們繼續看下去這一次微軟會用什麼角色來推動整個生態係吧！

https://twitter.com/vladcatrinescu/status/918605204160999424

https://www.microsoft.com/en-us/windows/windows-mixed-reality

-----
20171009

# [新奇] Babylon.js 搭配上 WebVR，讓你在 VR 環境內體驗 3D 遊戲

Edge 瀏覽器的換場動畫真的超炫的，然後只要用 Babylon.js 就可以快速的做出超讚的 WebVR 遊戲！

https://twitter.com/HoloLite/status/913839911962214400

------

# [技術] Babylon.js 深入淺出教學，就讓人一次就完成跨平台的 WebVR 3D 遊戲開發

Babylon.js 算是目前很火紅的框架之一，而這篇文章的作者則是從最基礎的各頭戴式顯示器與控制器的支援度到基礎的 WebVR 知識都有講解到。所以很推薦給不熟 WebVR 或是想要以 Babylon 開發得朋友看。

https://www.davrous.com/2017/07/07/from-zero-to-hero-creating-webvr-experiences-with-babylon-js-on-all-platforms/


------
# [專案] JanusWeb - JanusVR 的純 Web 客戶端，讓人可以在 3D 的環境下互動與聊天

現在的聊天不再像是過去一樣只是單純的聊天室，而是需要有更多的視覺上的衝擊與享受。像是這專案就是也採用了 Web 搭配 VR 的方式來體驗全 3D 的聊天與互動環境，其中還有人做出了一個過去大家熟悉的寶可夢場景出來。



https://github.com/jbaicoianu/janusweb

https://vesta.janusvr.com/popular/all/1

https://janusvr.com


-----
20171002

# [資訊] Mozilla 有關 VR 資訊的入口網站

如果你之前沒看過，現在讓你看了。畢竟整個編輯群都是 MozTW 社群的人，所以介紹一下 Mozilla 官方的 VR 資源一定是很正常的。

https://mozvr.com/

------
# [資訊] 一窺 BBC 實境實驗室在做什麼

> 在過去的兩年中 BBC 的研發工程師專注於透過 VR 技術並且在考量流程、技術、成本的狀況下來協助數位內容的產生。它們除了分享了有關製作 VR 內容的方式、以 360 攝影的新聞報導、設計字幕給 360 的資源與移植內容到多種不同的平台等等的相關知識。
 
BBC 真的是一個走在科技前端的新聞媒體平台，在文中它們除了有提到嘗試過使用各種新技術來實驗各種平台、資源對於媒體可能帶來的改變。更佩服的是 BBC 其下的 Reality Labs 更是一個開放標準的愛好者，它們除了答應會支持貢獻有關開放標準的生態系外，也會分享它們自己的實驗經驗。而 WebVR 也是 BBC 的 Reality Labs 關注的一環。
如果對於新聞業如何導入有關 VR 相關技術的朋友這篇非常值得參考。

http://www.bbc.co.uk/rd/blog/2017-09-bbc-reality-labs-virtual-augmented

------
# [技術] 沒看過龍貓嗎？現在讓你用 WebVR 看個夠

由於 A-Frame 0.7 後支援正多邊形 (NGon) 所以就可以支援 GoogleVR Blocks 所建模出來的 3D 模型。



https://twitter.com/Lady_Ada_King/status/912623897442439168/photo/1

https://vr.google.com/blocks/

https://github.com/archilogic-com/aframe-gblock

https://earthy-course.glitch.me/



------
# [專案] Networked-Aframe - 一個人玩 WebVR 已經不夠有趣，現在會寫 HTML 就能做出多人互動 WebVR 成品

A-Frame 可以算是目前最入門的 WebVR 框架，但只能一個人單獨體驗總是少了什麼。所以就出現了這個包含網路功能的 A-Frame 出來，然後最複雜的網路部分它已經用 node.js 中的 WebRTC 包裝起來。 因此開發者就只需要使用 HTML 就可以完成整個多人互動的 WebVR 成品而不需要理解底層的網路協定。


https://twitter.com/HaydenLee37/status/910183045537263616

https://github.com/haydenjameslee/networked-aframe

https://github.com/haydenjameslee/networked-aframe/blob/master/docs/getting-started-local.md

------

# [資訊] 去找吧！我把所有用 A-Frame 製作的 13K 遊戲都放在那裡了

前幾期提到的只用 13K 製作 javascript 遊戲的比賽，最近終於公開了比賽成品，大家真的要來讚嘆一下這些用不到 13K 就可以完成一個遊戲的開發者。

https://twitter.com/js13kGames/status/913769133136842753

http://2017.js13kgames.com/#winners-aframe


-----
20170918

# [趣味] 沒參加 Apple 發表會沒關係，用 WebVR 也有親臨 SteveJobs Theater 的震撼

AppleEvent2017 才正式公開的 Apple 新園區與 SteveJobs Theater 應該是很多蘋果粉絲必朝聖的景點，但不是每個人都有機會能參加 Apple 的發表會或是親自到訪來參觀園區。所以就有熱情的粉絲來幫忙建模出整個 SteveJobs Theater 的外觀與內裝，然後更棒的是在 VR 世界中也嵌入了發表會的影片，讓一切看起來更真實。

https://twitter.com/dburgauer/status/907646024348553218

http://project.archilogic.com/jobs-theater/


-----
# [技術] 不到 13K 的 WebVR 遊戲真的做的到，而且還超充裕！

在 Vol.16 時有提到「JS13KGames」這個超狂的競賽，然後竟然有開發者真的用 aframe 做了出了一個只有 6.5KB 的遊戲，然後還說到「13kb is quite a lot.」。這真的是太狂了，期待這位開發者把遊戲正式釋出的時刻。

https://twitter.com/Sorskoot/status/906524200076275714

-----
# [工具] Ottifox - 讓視覺設計師輕鬆設計 WebVR 的 Prototype 

> Ottifox 是一個專為設計師以視覺化製作 WebVR 場景的工具，用熟悉的 UI 方式來製作 prototype 並且可以直接使用瀏覽器來檢視效果。

這套讓設計師可以像使用 Sketch 或設計 App 的經驗來設計 WebVR 的場景，並且他也可以匯入各種的 3D 模組（如 .OBJ 格式）然後也可以自動化的將文字轉成 WebVR 所需要的格式。而最重要的是它可以直接接成果匯出成 A-Frame 的格式，讓開發者可以來再做更進一步的修改。

https://twitter.com/ottifox/status/907632252359655430

http://ottifox.com/

-----

# [技術] Microsoft Edge 即將在秋天支援 WebVR 的 motion controllers 應用

別在說微軟不上進了，現在的 Microsoft Edge 瀏覽器也是有一直在支援 WebVR 相關的應用。反而是蘋果的 Safari 目前才是對於 WebVR 支援度最低的平台。 


https://twitter.com/MSEdgeDev/status/908007998588559361

https://docs.microsoft.com/zh-tw/microsoft-edge/dev-guide/whats-new/edgehtml-16

-----

-----
# [趣味] 沒參加 Apple 發表會沒關係，用 WebVR 也有親臨 SteveJobs Theater 的震撼

AppleEvent2017 才正式公開的 Apple 新園區與 SteveJobs Theater 應該是很多蘋果粉絲必朝聖的景點，但不是每個人都有機會能參加 Apple 的發表會或是親自到訪來參觀園區。所以就有熱情的粉絲來幫忙建模出整個 SteveJobs Theater 的外觀與內裝，然後更棒的是在 VR 世界中也嵌入了發表會的影片，讓一切看起來更真實。

https://twitter.com/dburgauer/status/907646024348553218

http://project.archilogic.com/jobs-theater/

-----
# [有趣] 透過 WebAR 在家就能輕鬆預覽家具的擺設

傳統買家具都是以看型錄的尺寸後來丈量需要擺放的空間，但是透過 WebAR 的優勢，使用者就可以直接在畫面中確認空間大小並直接把虛擬的家具投射在畫面中。讓過去需要透過腦中想像的場景直接顯示在眼前，所以就可以減低各種不合適的可能性。

https://twitter.com/builtwithARCore/status/907507511259025408

-----
##### 20170916
# [服務]讓 CMS 系統不再是 Wordpress 統一天下，使用 VRiCMS 給讀者有不一樣閱讀 VR 體驗
現在討論到 Blog 系統大部分的人都會知道 Wordpress 這套內容管理系統（CMS），但在現今 WebVR 這麼火紅的時刻也當然不會缺席 CMS 這場盛會。因此目前就出現了一套名為 VRiCMS 的 VR 版本的 CMS。想當然的後台發文頁面也都還是使用傳統介面來顯示，但對於造訪網站的使用者來說就是可以立刻以 VR 視角來看網站文章。

雖然用 VR 看 Blog 是一件很潮的事情，但是如何讓使用者願意每次都用 VR 觀看與用 VR 觀看能多哪些不一樣的體驗就是值得站長去深思了。

https://vrimaginar.nl/nl/

https://twitter.com/VRimaginar/status/903011937352650752


-----

# [新奇] UpThere — 觀看星空不再困難，用 WebVR 來以太空角度觀看猶如真實的天象星空
> 傳統的天象儀讓人由地球的視角來看天上的星象，而 UpThere 則是透過三軸恆星的製圖法讓人感覺真實處在外太空中看星象。

過去的天象儀或是各種的星空投影都還是以地球的角度來看整個外太空。但是這套用 UpThere 則是讓自己身處在銀河系中，以外太空的角度來看星空的樣式。所以相對於傳統以地球的視角看會有更多不一樣的感覺出來。讓我們一起來體驗浩瀚無暇的宇宙吧

https://twitter.com/flimshaw/status/904897836323676160

http://uptherevr.com/

-----
# [資源] VRlist.io — 體驗 WebVR 的資源給好給滿
這一次推薦的 WebVR 資源比上回更多且更豐富，這網站所整理的專案除了有支援 Cardboard 的外也提供了支援 HTC Vive、Oculus 等高沉浸體驗的頭戴式設備。然後更酷的點在於這網站本來就是一個 WebVR Ready 的頁面，所以可以直接在 VR 環境下來選擇自己想要體驗哪一些的 WebVR 專案。

http://vrlist.io/

-----
##### 20170831

# [工具] Hologram - 比 A-Frame 更入門的 WebVR 創作工具

Hologram 是一套採用所見即所得操作方式的圖形化 WebVR 創作工具，過去在 A-Frame 開發最不直覺的是需要自己去尋找 3D 模型並手動匯入，但在 Hologram 連接了 sketchfab 這 3D 模型的素材庫，所以只要點幾個按鍵就選擇喜歡的素材就可以匯入到目前的專案。基本上使用 Hologram 來開發 WebVR 是真的可以達到用拖拉方式完成一份屬於自己的專案，有興趣的就快來試試吧！

對了，這應用程式目前只支援 macOS，所以 Windows 或是其他系統的用戶就只能先說聲抱歉了。

https://hologram.cool/

----

# [服務]讓 CMS 系統不再是 Wordpress 統一天下，使用 VRiCMS 給讀者有不一樣閱讀 VR 體驗

現在討論到 Blog 系統大部分的人都會知道 Wordpress 這套內容管理系統（CMS），但在現今 WebVR 這麼火紅的時刻也當然不會缺席 CMS 這場盛會。因此目前就出現了一套名為 VRiCMS 的 VR 版本的 CMS。想當然的後台發文頁面也都還是使用傳統介面來顯示，但對於造訪網站的使用者來說就是可以立刻以 VR 視角來看網站文章。

雖然用 VR 看 Blog 是一件很潮的事情，但是如何讓使用者願意每次都用 VR 觀看與用 VR 觀看能多哪些不一樣的體驗就是值得站長去深思了。

https://vrimaginar.nl/nl/

https://twitter.com/VRimaginar/status/903011937352650752

----

# [資訊] Mozilla 技術人員整理出來的 WebVR 資訊新手懶人包

就在 Firefox 55 正式支援 WebVR 後，越來越多人對於 WebVR 有興趣但是資料真的很雜很亂。所以 Mozilla 就整理出來一些給新手最基本的文件與 DEMO Project 來源。當然這些資源都是英文的，所以如果看不懂也是歡迎來看我們的 [webvr.tw](http://webvr.tw/)  來獲取更多有關 WebVr 的正體中文資訊喔！

https://hacks.mozilla.org/2017/08/essential-webvr-resources/

----

-----
##### 20170824


# [工具] 想用手機建模 WebVR 的物件雛形？沒問題，現在用 threejs 就可以辦到

目前用 three.js 的網頁編輯器就可以簡單且即時的用手機瀏覽器即時做出 WebVR 中的 3D 物件，更棒的是能直接在網頁上開啟 VR 模式，只要戴上 Cardboard 或是其他頭戴式設備就可以立刻看到剛剛自己用 WebVR 所建模出來的元件。

https://twitter.com/mrdoob/status/900148390339649536

https://threejs.org/editor/

----
# [實用] Google 提供專屬 WebVR 的 "酷酷小物" 網頁平台

隨著 WebVR 技術發展，各項 VR 設備也越來越普及，至少你可以輕易在網路上花幾百元買個 Cardboard 回來玩。由於讓大家能體驗到 WebVR 的酷炫與應用才是推廣最有利的方式，因此 Google 建立了一個名為 WebVR Experiments 的網站，專門用來收集各種有趣或是惡趣的 WebVR 互動體驗，讓一般的使用者可以體驗 WebVR 的樂趣與驚艷。
這個網站其實好一陣子了，過往我們也報導過不少其中的體驗，但這次就直接通通貼出來讓你玩啦！

https://techcrunch.com/2017/04/12/google-launches-a-dedicated-home-for-webvr-experiences/

https://experiments.withgoogle.com/webvr


-----
#[觀點] WebVR 對世界三種行業的改變

這篇文章是一家用 React 開發前端應用的公司 rangle.io 所寫的願景文。它們預期到 2020 年 VR 與 AR 的總產值會達到 295 億美金的市場規模。也因此它們預估了三種最有可能讓 WebVR 帶來大量改變的行業。
第一個是房地產業，因為當賣家戴上頭戴顯示器，他就可以不用到現場也可以直接看到房子內部的空間感與景色，然後更重要的是他還可以直接在 VR 環境中修改自己想要的房間配色與家具擺飾，這些都是過去在現場看實景所無法做到的部分。
而第二種則是零售業，目前線上購物是一個非常成熟的產業，但如果搭上 WebVR 則可以讓使用者感覺到自己真的在逛接，因為不再只能看商品平面的照片而是可以各項商品的實際比例與 3D 立體樣式，能讓使用者更感覺到該商品的真實性。
最後提到的則是多媒體產業，因為像是美國電信商 Verizon 目前就已經開始提供 360 度的多媒體影音搭配 VR 來提供給消費者選擇。
當然結尾我們可以看到這家公司還是在推銷自家 React VR 來做 WebVR 有多多的可能性。但不能否認的，當 WebVR 開始普及到一般人的生活時，會有越來越多東西不需要自己親臨現場也能體驗到相同的感受與震撼力。

http://blog.rangle.io/imagining-3-real-world-applications-for-webvr/

----
