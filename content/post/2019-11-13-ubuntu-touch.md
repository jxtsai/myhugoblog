+++
date = "2019-11-13 02:04:00+00:00"
draft = false
title = "Ubuntu Touch 安裝試用"
slug = "ubuntu-Touch"
categories = ["blogging"]
tags = [
  "nexus",
  "ubuntu"
  ]
disable_profile = false
disable_widgets = false
+++

本週入手 7 年前上市的 nexus 4 中古機。二年多前入手 Nexus Galaxy, 並將之[改刷成 Lineage OS](https://blog.jxtsai.info/post/-nexus4-cmod13/)，雖然不小心把螢幕摔裂也多多少少有些老毛病，但還是喜歡這支機子，故一直想要找同系列的替代品。最近終於遇到心中屬意且價格便宜的 Nexus 4，正好利用它來安裝移動版 ubuntu(ubuntu touch, 以下稱 UT)。
<!--more-->

2012 年 11 月問市的 nexus 4 是由 LG 代工，Google 血統認證的第四個親生子。因這身份讓許多安卓軟體開發者樂於利用它們來改造、開發手機作業系統，即使上市多年後原廠已不再支援該設備維護更新，但仍有許多志工熱心地默默投入。例如 Google 官方支源到 Android 5.1，但在 LineageOS 可以找到 16 版(約莫是 Android 8.1)。

## Nexus 4 基本資料
收到這台 nexus 4 手機時其作業系統已是 LineageOS 16.1，但無安裝 Gapps，故可知該手機已 root (開放管理者最高權限,可刪改軟體)，也載裝了新近的[TWRP](https://zh.wikipedia.org/zh-tw/TWRP)軟體版本。 TWRP 其全名文: Team Win Recovery Project 可知其為一個客製化恢復模式映像( recovery), 允許用戶向第三方安裝韌體和備份目前的系統。 

由於前手安裝的 LineageOS 並未附 GoogleApps，就是無法利用 Google Account 架構透過 Google Play 方便下載安裝各式軟體，故試著刷入 Open Gapps(其作法是進入 recovery mode，然後安裝剛下載的 Gapps 壓縮包)。但不知為什麼自己刷入 Gapps 過程並不順遂，再次開機後反覆出現 Google Account/ Google Play 出錯等訊息視窗。憤而移除 Gapps，結果在幾次重複進入 recovery mode 程序中不小心把手機上的資料(除了TWRP)都給刪掉了，其下場就是按電源後出現 google logo 畫面，卻無法進入作業系統，也就是俗稱的「變磚」Orz..... 

這時候將已磚化只能強制關機的 Nexus 4 以 USB 線連接電腦，電腦站還可以正確偵測到此設備。因此先試著把 LineageOS Rom 複製到 N4 內建記憶卡上，試圖以「卡刷」方式救機，試了15, 16 二個版本皆以失敗告終。

850 元入手的新玩具還不到三小時就被弄成磚塊，心裏倒是不太緊張，因為這類原生機應有不少搶救的資訊，如卡刷失敗應該可以再試試「線刷」方式，姑且先把機子晾在一旁，等空閒再來研究如何救磚。

在變磚之前，第一個玩機動作是在 linux mint 透過 UBports Installer 試圖以傻瓜法安裝 ubuntu touch，但在 fastboot  畫面卡了很久，只好放棄。在進入線刷搶救前，心想反正死馬當活馬醫。不如先來試試能否改以在 windows 作業系統下來刷入 ubuntu touch，結果居然姑且一試就無痛把 UT 給安裝在 N4，其過程重述如下:

## ubuntu touch 安裝

直接下載符合電腦作業程式的 [UBports Installer](https://ubuntu-toouch.io) ，開啟此軟體執行後讓電腦透過 USB 線連接手機，此刻手機為關機狀態。先在電腦上選擇欲安裝 UT 的設備機種後，同時按住手機音量鍵下方與電源鍵，讓 N4 進入 fastboot 。
![](https://i.imgur.com/wI0qTKQ.png)

![](https://i.imgur.com/GaWqJsg.jpg)


這時候看到電腦上的 UBports Installer 狀態有出現正在下載 UT 的進度，另一端手機也從上圖的 fastbook 模式變成為進入 UT recovery 模式(下方第二圖)。這是在手機 USB 連接桌機 linux Mint系統時並未出現的反應，感覺有戲故耐心等待其下載完成後，UBports Installer跳入顯示正在把檔案接送到手機的狀態。

![](https://i.imgur.com/KLvHbcb.png)

![](https://i.imgur.com/PMPdlgQ.jpg)

![](https://i.imgur.com/cKB0bog.png)

等完成線接的檔案傳送後，N4 就開始自行進入安裝重啟的狀態，首次開機需稍等較久，然後就順利進入 UT 作業系統。下圖中的序列號與 IMEI 資訊為刻意隱去處理，至於 Last updated 時間則為 UNIX Time。

![](https://i.imgur.com/fPsXqO2.png)


## UT 初體驗
UT 支援多語系介面，其內建的中文輸入為 chewing 新酷音。

![](https://i.imgur.com/HgBWxuM.png)


習慣iOS / Android 智慧型手機者，在全新的移動設備作業環境下，最關心的大概就是它有沒有類似 Apple Store/ Google Play 之類的軟體集散平台。在 UT 這類功能，就是 [Open Store](https://open-store.io/),光從網站上列名的軟體清單即可知道不少是屬於 Web Apps，也就寄生在瀏覽器環境下的軟體服務。 (關於 Web App/ Native Apps 的異同可參考[此文](https://www.lifewire.com/native-apps-vs-web-apps-2373133))

整體而言 web apps 在用戶體驗上明顯劣於 native apps，以  Gmail 為例， web app 讀取信件內容時，常常會因為電子報郵件排版無法照手機瀏覽器大小響應為信件圖片取得最佳閱讀瀏覽效果。同一封郵件，以下二圖前者是在 Nexus 4 Gmail Web App 信件內容無法自動適應手機畫面照片文字被切成一半;而後者則為 Nexus Galaxy Gmail Native App，同一郵件可說是完美地呈現在手機 4.7"的螢幕上。

![](https://i.imgur.com/evIbFVP.png)

![](https://i.imgur.com/AmCo9H9.png)


玩過 ubuntu 桌面者，應該不難體會 UT 為作其觸控式改良的使用者介面與體驗感，運行在桌機筆電還是手機 [unity 桌面](https://en.wikipedia.org/wiki/Unity_(user_interface))二者的相似度極高。據說 UT 矢志以打造一個尊重用戶資料與隱私為優先的移動作業環境，但目前欠缺活躍的原生應用開發社群，主要依賴 Web Apps 移殖，故手機瀏覽器的安全與重要性不言可喻。

![](https://i.imgur.com/l59L5Ui.jpg)


本人手機使用習慣和 20 年前用無法通話的 PDA 差不多, 鮮少打電話傳簡訊，使用量最大軟體約莫: 看看 twitter 即時動態, pocket/RSS 閱讀網頁長文, sportscore 關心體育賽事比分, podcast..... 故兩天簡單的體驗心得：這種實驗性非主流的開源軟體，長期欠缺足裕的資源來打造最完美的體驗，即便軟體目前使用上有嚴重瑕疵，不知哪一天開發者才會處置改善。UT 目前最適合的使用族群，大概就是我這種不用智慧型手機打卡晒圖話嘮的老派人士吧，需要傳賴打卡美圖者，就不必費心看此文了。


