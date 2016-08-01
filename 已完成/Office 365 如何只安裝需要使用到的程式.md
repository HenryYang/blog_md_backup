Office 365 如何只安裝需要使用到的程式 (Office 2016 也可使用)
====

新款的 Office 為了簡化安裝流程，所以點下安裝後就直接一路安裝到底，並沒有提供像是過去一樣的自訂安裝選項，所以對於硬碟空間不足或是只想安裝特定程式的人其實很困擾。

![](https://photo.hy31.net/2015/office/2016install/1.png)
![](https://photo.hy31.net/2015/office/2016install/2.png)



所以要自訂安裝的人，可以透過 Office 的部屬工具 (Office 2016 Deployment Tool) 來製作自己想要的安裝包。這樣的好處是，你只要自備好授權（序號或是具有 Office365 全權限的帳號），不用先行下載好肥大的 Office 安裝程式，透過部屬工具就可以線上下載你所需要的程式而已，然後安裝後套用自己的正版授權就完成了。



Step1: [下載 Office 的部屬工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)，並解壓縮，然後你會看到2個檔案

![](https://photo.hy31.net/2015/office/2016install/3.png)


Step2: 製作你的部屬設定檔，因為預設的 configuration.xml 是空的，所以可以直接從我的 [Gist](https://gist.github.com/HenryYang/ff456a0bac2b9c877ada) 把我的版本拉下來直接使用或是再做調整

![](https://photo.hy31.net/2015/office/2016install/6.png)


打開後會看到下面的 XML 語法：

SourcePath 為空的話就是把檔案存在跟文件同一個目錄下，如果沒有特別需求其實不用動。

OfficeClientEdition 就是看要安裝 **32** 還是 **64** 位元，請自己修改

Product ID 是比較重要的東西，因為這會攸關到授權的版本，詳細的可以參考[微軟網站](https://support.microsoft.com/en-us/kb/2842297)。一般來說，個人買到的Office 365 方案（如 Office ProPlus 、Office 365 Enterprise E3、Office 365 Enterprise E4、Office 365 Midsize ）都是選擇 **O365ProPlusRetail**
，而 Business 授權才是選擇 **O365BusinessRetail** 或是 **O365SmallBusPremRetail**

Language ID 則是安裝的語言，繁體中文是 **zh-tw**，而英文是**en-us**
ExcludeApp ID 則是不要安裝的程式，就是加上去你不要安裝的程式名稱就可以

Step3: 下載與部署檔案
把命令提示字元切到解壓縮後的目錄，執行以下指令就會開始下載所需要的 Office 程式，等程式執行結束後就會多出一個 Office 的資料夾，這就是安裝所需要的檔案
>setup.exe /download Office365_configuration.xml

![](https://photo.hy31.net/2015/office/2016install/4.png)


而再下載完後再執行以下指令，就會開始安裝你的 Office 了，然後安裝完後可以把這資料夾整個複製走，下回要重灌只要在新電腦再次執行下面的指令就可以直接安裝，不用重做上述的步驟
>setup.exe /configure Office365_configuration.xml

![](https://photo.hy31.net/2015/office/2016install/5.png)



參考資料：
http://demo.tc/post/819
https://www.facebook.com/jaschiang/posts/10206477809277514?pnref=story
