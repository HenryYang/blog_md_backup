Linux 主機 熱轉移到 Esxi 虛擬機上的注意事項
====
 

我是用 VMware vCenter Converter Standalone 來將我的 Ubuntu 14.04 主機轉移到 Esxi 主機變成虛擬機

以下是幾點遇到要注意的事項

*	Converter Standalone Client 需要用系統管理員執行才可以
* 	欲轉換的主機一定要用 root 帳號登入，所以需要去 ssh 設定允許遠端 root 登入
*  轉換成VM時的硬碟空間要抓對，不然可能會因為空間不足轉換失敗
*  這套軟體熱轉移的作法是先在 ESXI 上開一台 VM 上面跑他專屬的 Linux用來傳輸與接收檔案，所以一定要給一個實體主機主機連的到的IP在虛擬機上，我當時就是因為之後要換網段，然後又以為轉換時設定的IP是會直接寫入虛擬機，所以把實體主機與虛擬機設定在不同網段，當然熱轉移會失敗，因為根本找不到目的地的主機。

