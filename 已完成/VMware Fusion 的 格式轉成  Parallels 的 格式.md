OSX 上的虛擬機映象檔互相轉換
====

目前 Mac 上主流的虛擬機軟體主要有 VMware Fusion 、 Parallels Desktop、 VirtualBox 這三大家，但尤其以 Parallels Desktop 為目前 OSX 最多人在使用的虛擬機器。

而大家常遇到的問題會是說，在 Windows 上最熱門的虛擬機器反而是 VMware 公司所推出的，因此當轉換虛擬機軟體時就同時需要將自己的虛擬機映象檔做轉檔才能給另一套軟體執行。

本篇教學將分為：

1. Parallels Desktop 的映象檔轉換到 VMware 上面執行
2. VMware 的映象檔轉換到 Parallels Desktop 上面運行


註：這邊 OS 是使用 Windows 10 做示範， Parallels Desktop 版本為 11 ， VMware Fusion 版本為 8
 

##教學： Parallels To VMware

Step.1 雖然我們是要轉換 Parallels 的映象檔，但是因為目標是轉成 VMware格式，所以我們直接打開 VMware Fusion 這軟體，然後選擇 File -> Import ，然後理論上 VMware 會直接偵測到你的 Parallels 的映象檔，如果沒有的話就可以點選中間的 Choose File 來手動選擇。

![](https://photo.hy31.net/2015/VM/001.png)
![](https://photo.hy31.net/2015/VM/002.png)


Step.2 接下來就是設定檔案名稱，然後要記得轉檔時 Parallels 主程式要關閉才不會報錯。


![](https://photo.hy31.net/2015/VM/003.png)
![](https://photo.hy31.net/2015/VM/004.png)




Step.3 然後就是等 VMware 來轉換，這會跟電腦效能有非常大的關係，而只要沒有問題，最後就會跳出 Finish 字樣，這樣就算是完成了。然後他會依照你的系統給予虛擬機器設定值，如果不喜歡，可以按下 Customize Settings 來修改。


![](https://photo.hy31.net/2015/VM/005.png)
![](https://photo.hy31.net/2015/VM/006.png)

Step.4 轉換完之後就可以在 VMware 上把虛擬機器打開，然後第一次登入後請不要做任何事情，因為 VMware 會自己安裝所需的驅動程式，然後最重要的就是要把 Parallels 的驅動程式砍掉，不然可能會有相衝的可能性，這樣就算是完成的虛擬機映象檔的轉移了。


![](https://photo.hy31.net/2015/VM/007.png)
![](https://photo.hy31.net/2015/VM/008.png)



##教學： VMware To Parallels

Step.1 把 VMware 的檔案轉換到 Parallels 其實更簡單，可以更直覺的選擇 文件->開啟 ，選取 VMware 的映象檔就直接會幫你轉換與設定了。


![](https://photo.hy31.net/2015/VM/009.png)
![](https://photo.hy31.net/2015/VM/010.png)
![](https://photo.hy31.net/2015/VM/011.png)


Step.2 這邊要注意的是，Parallels的輔助程式會再轉換期間就安裝，所以如果你的系統有登入密碼要記得手動輸入，不要傻傻的放在那邊等它跑。


![](https://photo.hy31.net/2015/VM/012.png)


Step.3 輸入完密碼後就會再轉換期間幫你設定與安裝好所需的驅動與軟體。

![](https://photo.hy31.net/2015/VM/013.png)
![](https://photo.hy31.net/2015/VM/014.png)


Step.4 同要要記得的是第一次把虛擬機器打開要去把 VMware 的驅動程式砍掉，這樣就算是完成的虛擬機映象檔的轉移了。

![](https://photo.hy31.net/2015/VM/016.png)


