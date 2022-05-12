+++
date = "2017-12-18 21:14:00+00:00"
draft = false
title = "Galaxy Nexus 昇級 LineageOS 13"
slug = " Nexus4-CMod13"
categories = ["internet"]
tags = [
  "android",
  "Lineageos"
  ]
disable_profile = false
disable_widgets = false
+++
繼前一天太過輕易地成功把四年的老機子 [Samsung Tab4 昇級到 Android 6.0](https://blog.jxtsai.info/2017/12/16/t235y-cmod13/) 之後，心裏便按耐不住地也想替手上主要使用的 Galaxy Nexus 進行一番昇級。為了日後重覆操作或再次昇級之需，還是把這回刷機過程記錄下來。 

<!--more-->
這支 2011 年上市的  Galaxy Nexus 手機，是我今年夏初購入的二手貨。它本身是 google 的親兒子，效能與規格在當時皆為一時之選，即便在六年之後此等規格仍然大大符合我個人的使用需求與偏好（尤其無法接受螢幕 5 吋以上的手機），且原手機機主保存的機況還算不錯，自己僅用了一千元入手。記得當時此機並未 root，也維持在 Samsung 最後更新的版本 -- Android 4.3。

拿到機子後，我找了卡刷的方式把它昇級到了 4.4，而試圖再繼續昇級到 5.0 以上等版本，則會卡關失敗。又看不太懂在 Linux 作業環境下如何進行線刷，故入手的半年多來，一直「將就著」使用 Android 4.4。

在刷機之前先透過 root check 檢查，確認這隻手機並未取得 root 最高權限，所以花了一點時間找尋網路上流傳的解開權限作法。原本想依照這個網站[galaxynexusroot.com](http://galaxynexusroot.com/) 在 linux 作業環境下操作，但下載回來的解壓縮檔案目錄卻無法執行 fastboot 程式指令，只好轉退到 windows 作業環境下，利用 Nexus Root Toolkit 方式進行。詳細的步驟教學可參考[這篇詳細的圖文介紹（中文）](http://izaka.tw/2013-06-27-173/)。其中我覺得最煩瑣的部份，不是 Root Toolkit 操作，反而是如何讓 windows 可以順利地安裝相關驅動程式，以成功讓 ADB/Fastboot 透過 USB 接口可以偵測到 Galaxy Nexus 的連接正常，才可以進行「解鎖」、 root 、刷入 TWRP (for recovery)、 SuperSU、Busybox 等程式。光是搞定驅動程式，大約就佔了這回刷機手續總時間的三分之二吧 (￣口￣)!!

順利取得 root 最高管理員權限，並安裝好 TWRP 作為手機系統預設的 recovery 操作軟體後，接下來則是去找到合適可裝在這款手機上的 ROM。Android 各式 ROM 開發分享的集散地 xda-developers 即針對這款當年的機王有一處[討論交流專區](https://forum.xda-developers.com/galaxy-nexus)，上頭有著不少資源。而我所挑選使用的版本則是宣稱為 [LineageOS 13.0 的正式發佈版](https://forum.xda-developers.com/galaxy-nexus/development/rom-cyanogenmod-13-0-02-11-t3312784)。  

同樣也是依照之前刷 Samsumg Tab4 的步驟，把 CM13 ROM, Google Apps 的壓縮檔下載後，儲存到這支手機內建的儲存空間上（此款手機並無支援 micro-sd 插槽）。關機後，進入 recovery 模式（同時按住 volume up + volume down + power），因為前面已順利安裝好 TWRP ，所以進入 recovery 狀態會看到的是類似下方的畫面：

![](/post/2017121801.jpeg)

在 TWRP 模式下，先選擇「Wipe」為手機作一番資料清理，否則新的 ROM　刷不進去。（我是直接在「wipe」底下選擇“factory reset”）

回到 TWRP 主選單中，接下來選擇「Install」選項，並指定儲存在手機上的 CM13 ROM zip 檔。此步驟大約費時 3~5分鐘，沒什麼大問題的話，就會出現 success 的成功訊息。

再一次重覆選擇「Install」，這回要刷入的 google apps，此步驟也差不多要費時3~5分鐘。分別成功刷入 CM13 與 google apps 後，返回 TWRP 主選單選擇「Reboot」重新開機，第一次啟動新系統可能會稍久一點，大約 7～10分鐘，手機畫面出現的訊息是系統正在一一安裝各種手機上應用，大約有 90 多個程式應用安裝完畢後，就可順利入 CM 13 系統，當然第一次登入新系統時，會出現設定精靈引導新用戶一步一步完成無線連線訊號、電信數據、google 帳號等設定動作。

![](/post/2017121802.png)


寫起來，好像這番昇級的手續很是簡單。的確刷機並不困難，比較麻煩的是這隻現役手機上的 google authenticator 已綁定十多個網路服務的雙因子認證。要刪除手機資料之前，還得花上不少時間一一去暫時解除這些網路服務的 2FA。等到昇級更新完畢後，再重新安裝  google authenticator 並重新進行一輪 Two Factor Authentication 的設定～～
