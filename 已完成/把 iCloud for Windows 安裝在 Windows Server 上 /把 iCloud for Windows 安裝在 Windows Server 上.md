# 把 iCloud for Windows 安裝在 Windows Server 上 

過去我是使用 Xmarks 來同步書籤，但是現在要同步行動端的是需要付費而且 Xmarks 需要在手機端另外多裝一個 App ，所以一直再找替代方案。

最近找到[一篇可以免費同步書籤的方式（iCloud 完美同步合併 Firefox Chrome Safari 書籤實測教學 By 電腦玩物）](http://www.playpcesor.com/2013/09/icloud-firefox-chrome-safari.html)，就是透過 iCloud 的幫助來達成的，但是這之所以沒有被廣泛使用也是有原因的，因為他需要把程式一直開著才會執行同步，因此你需要有一台幾乎永遠不關機的電腦。

但矛盾的點就在這邊，通常我們不關機的 Windows 都會是 Server 版本，但是 iCloud for Windows 卻只支援一般版本的 Windows ，所以本篇教學主要著重在如何在 Windows Server 上安裝 iCloud for Windows 程式，至於如何透過 iCloud 同步書籤就請參考上面的連結。



本篇以 Windows Server 2012 R2 64 bit 為示範環境

步驟一：下載所需軟體

* [iCloud for Windows](https://support.apple.com/zh-tw/HT204283)
* [Ocra - 用來修改 msi 檔案資訊](https://msdn.microsoft.com/zh-tw/library/aa370557.aspx)
* 任一套解壓縮軟體

步驟二：拆解出 iCloud for Windows 所需檔案

把從蘋果官網下載的 icloudsetup.exe 用任一套解壓縮軟體開啟後把 AppleApplicationSupport.msi 與 iCloud64.msi 收取出來放在你的桌面，然後用 Ocra 開啟剛剛解壓縮出來的 iCloud64.msi ，這時候你應該會看到這樣的畫面

![](https://photo.hy31.net/2016/iCloud/1.png)

這時候請選擇左方列表中的 LaunchCondition ，並且找到

```sh
(VersionNT \>= 601) AND (MsiNTProductType = 1)"
```

這組值，然後將(MsiNTProductType = 1)中的 1 改成 3 ，然後確認該欄位數值是

```sh
(VersionNT \>= 601) AND (MsiNTProductType = 3)
```

就存檔然後把 Ocra 這程式關閉了。

步驟三：檢查電腦是否安裝的 Media Player

按下開始按鈕去程式集內看看電腦是否有安裝 Media Player 的元件，如果你的電腦沒有安裝，就要去伺服器管理員中新增桌面體驗功能。

點選伺服器管理員，然後選擇右上方的新增功能與角色，然後一直點下一步直到 ”功能”
![](https://photo.hy31.net/2016/iCloud/3.png)
![](https://photo.hy31.net/2016/iCloud/4.png)
這部分，然後將使用者介面與基礎架構中的桌面體驗 打勾，然後安裝他，安裝成功後重開機就可以在程式集中找到 Media Player

步驟四：安裝吧！

如果前面的步驟都有做對，現在請依序先安裝AppleApplicationSupport.msi 再安裝 iCloud64.msi ，完成後重開機，就可以讓 iCloud For Windows 跑在 Windows Server 上了。

![](https://photo.hy31.net/2016/iCloud/2.png)
![](https://photo.hy31.net/2016/iCloud/98.png)
![](https://photo.hy31.net/2016/iCloud/99.png)

如果你信任我（？！）

可以直接下載我修改好的[iCloud64.msi](https://www.dropbox.com/s/1lc0kzaujvz4eie/iCloud64.msi?dl=1)與[AppleApplicationSupport.msi](https://www.dropbox.com/s/bfr4yaqik5ou20h/AppleApplicationSupport.msi?dl=1)



