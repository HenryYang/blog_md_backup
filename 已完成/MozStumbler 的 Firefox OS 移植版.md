MozStumbler 的 Firefox OS 移植版 - FxStumbler
====


MozStumbler 是用來協助 [Mozilla Location Service (MLS)](https://location.services.mozilla.com/)來做定位服務的資料收集。

像是目前Google Maps就有利用搜尋附近無線基地台跟電信基地台方式協助在GPS收訊不良時的定位，而MLS也是希望使用者能有更多與更開放的選擇，因此也開始執行這個實驗性質的Geolocation計畫。



透過MozStumbler這套軟體，在程式開啟後，會在背景蒐集GPS、WiFi基地台、電信基地台的資訊，然後程式會自動將資料回傳回去，這樣就可以協助Mozilla建立以網路架構為基礎的定位服務，當然，這比其他服務開放 :)


目前能幫MLS提供定位資訊的為 Android 與 Firefox OS 平台

## Android 安裝方式

* 透過[Google Play](https://play.google.com/store/apps/details?id=org.mozilla.mozstumbler&hl=zh_TW)下載

使用方式非常簡單，安裝後，打開它。然後只要確認右上方藍色開啟字樣就代表有在紀錄了。

![](https://photo.hy31.net/2015/mozstunbler/201502200001.jpg)



## Firefox OS 安裝方式

**這邊安裝的是名為[FxStumbler](https://github.com/clochix/FxStumbler)的第三方的版本**

####安裝步驟

1. 將FxStumbler在GitHub上的[repo](https://github.com/clochix/FxStumbler)抓下來，有安裝git的可以用git clone，如果沒有安裝過的可以直接按右方的 Download ZIP下載並且解壓縮。

2. 把你的Firefox打開並選擇 工具 - 網頁開發者 - WebIDE

	![](https://photo.hy31.net/2015/mozstunbler/201502200004.png)


3. 點選左上方的箭頭，選擇 開啟封裝的應用程式 

	![](https://photo.hy31.net/2015/mozstunbler/201502200005.png)

4. 看到專案入載後，按下右邊的 選擇Runtime，選擇你的Firefox OS手機，然後按下中間的執行按扭

	![](https://photo.hy31.net/2015/mozstunbler/201502200006.png)

5. 接下來在手機上就可以看到FxStumbler這App，然後Enjoy :) 

	![](https://photo.hy31.net/2015/mozstunbler/201502200002.png)

	![](https://photo.hy31.net/2015/mozstunbler/201502200003.png)


