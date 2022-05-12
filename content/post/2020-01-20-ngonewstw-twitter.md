+++
date = "2020-01-20 02:04:00+00:00"
draft = false
title = "NGONewsTW 推特帳號更新之二三事"
slug = "ngonewstw-update-2020"
categories = ["internet"]
tags = [
  "IFTTT",
  "zapier",
  "Power Automate",
  "twitter",
  "ngonewstw"
  ]
disable_profile = false
disable_widgets = false
+++

三年前仿效 [@GOVNewsTW](https://twitter.com/govnewstw) 利用 IFTTT 抓取台灣近百家倡議型非政府組織網站的最新訊息推送(RSS/feed)推送到 twitter 來發佈、記錄台灣非營利組織的官網訊息動態。雖然最初動機目的完全只是為了方便自己快速地瀏覧知悉台灣各家 NGOs 近期在推動關心什麼話題，但它也慢慢地累積了超過 300 多位的追踪訂閱者（含 mastodon）。當然 300　可能還是灌過水純度低的數字，一點也起不到什麼網路聲量，此帳號姑且視為這個網路社群交界時代的一點㾗跡吧。

<!--more-->

2020 年 1 月初接到 twitter 通知，懷疑它是垃圾推文機器人帳號，要求提供手機門號驗證。雖然照著 twitter 要求，但遲遲未收到驗證碼，便按正常程序規矩，在客戶支援處提交了協助處理的申訴信。在此帳號停用期間，心想先移除 IFTTT 與 @NGONewsTW 之間的綁定關係，卻沒料到一不小心就把與 twitter 有關的上百個 applets 全部給自動刪除了（哭……）。約莫十天後，才收到 twitter 客服回覆，表示他們誤判 @NGONewsTW 為垃圾推文機器人,重新恢復此帳號正常登錄推文功能。但此時面對一片空白寂寥的 IFTTT ，雖心冷不已但畢竟得滿足自己局外人至少有一個簡單的窗口來窺探台灣公民社會動態，只能耐著脾氣來重新整理帳號初期所建立的[台灣非政府組織網站資訊列表](https://to.twngo.xyz/lists)與相關自動化流程。

![](https://i.imgur.com/csQf4fE.png)

#### 訊息類型 

目前 @NGONewsTW 推送的訊息類型有三類

1.  NGOs 官網的最新消息，須有支援 RSS 新文推送者。如果網站架設系統是 WordPress 或是以 blogger 指向自定域名者，當然都支援 RSS。WP 應是國外內最流行的架站軟體。 另一個 Drupal 近五六年來在台灣也算是「異軍突起」，大概不脫行動網絡科技整合 civicrm 系統的推廣。順便統計一下台灣非政府組織大略網站架設軟體的使用狀況：所收集的一百八十家左右的倡議型非政府組織，其網站後台管理的軟體架構使用情況。當中約三成無法判別網站使用何種架設軟體，如果這三成中又沒有 RWD( responsive web design) 多半十年以上未改版更新的老舊型網站，但網站老舊與 NGO 本身財務狀況似乎看不出明顯的關係，倒是與組織的活躍度與網路聲量比較有關吧？（完全不準確的個人主觀意見）

![](https://i.imgur.com/RDVqieS.png)

2.  NGOs Youtube 影片發佈。 YT 作為年青人黏著時間最多的平台，已慢慢成為不少非營利組織必經營的網路戰場。就算不刻意經營，用來直播、記錄、儲放組織的多媒體影片也非常簡易好用。 IFTTT 提供了自動讓用戶在所訂閱的頻道有發佈新影片內容時可以觸發另一款網路應用動作(下圖第一排右二選項)，就透過新推文代 NGOs 公告某支 YT 新影片上線。 ![](https://i.imgur.com/bOg9y3g.png)
    
3.  各家 NGO 推特發文。既然選用 twitter/mastodon 作為上述台灣非政府組織訊息的聚合發佈管道，當然要來和有使用 twitter 的 NGOs 互動示好。據說 twitter 在台灣上網人口的使用率大約是 6~7 %，我盡力在推特裏人工地上海下地搜尋台灣非政府組織有開推特帳號的[名單整理](https://twitter.com/NGOnewsTW/lists/tw-ngos)。當然這類訊息並不是清單上的每一個帳號都會轉發，畢竟有些 NGO 推特帳號似乎死去已久，甚至某些組織團體運動早已人去樓空。而有些積極活躍的帳號則建議推友們可以直接關注， @NGONewsTW 不必代之畫蛇添足。
    

其它更主流更受國人歡迎的 Facebook, instagram, line，因為自己根本不用，故沒花時間了解在其中流竄的台灣 NGO 訊息，更遑論費力收集整理。

#### Automation 工具說明 

隨著 IFTTT 去年年底介面改革與政策調整，免費用戶可享的功能開始受到限制，例如推持一天的發文上限是 25 則。正因收集台灣非營利組織即時資訊的擴充，要達到一天隨隨便便 25 則推文可說是輕而易舉。為了解決會被 IFTTT 限制發推的困境，遂摸索其它類似 IFTTT 網路自動化替代服務，如 zapier, Microsoft Power Automate，zoho flow 等。有興趣想了解此類 automation 網路服務的比較，可參考此篇文章[Codeless Automation: IFTTT vs Zapier vs Microsoft Flow](https://medium.com/better-programming/codeless-automation-ifttt-vs-zapier-vs-microsoft-flow-57d5bc56fc0e)

這回依照各家網站的 CMS 與訊息發佈管道來分散 IFTTT 依賴，例如大部份官網 RSS 是透過 MS power automate（drupal 網站除外），而 youtube 新影片發佈、推特發文則透過 IFTTT，順便再利用一下 buffer 的時程發佈與 [bitly 的自定網址域名縮短功能](https://to.twngo.xyz/05132017)。

下圖是在 MS power automate 上設定 RSS 觸發到 twitter 的流程。一開始摸 MS power automate 被上面那篇評比文唬得以為會太難，但多試了幾個流程之後，才慢慢感到 power automate 比之 IFTTT 的強大勝出之處，例如 IFTTT 只能允許二個不同應用的串接，而 power automate 一個流程可以串接多款應用。zapiter 雖然也很強大，但免費版也是只支援二個動作，且僅能製作 5 個 zapier，所以 MS power automate 就成了我的新歡。 ![](https://i.imgur.com/Uvd8zQr.png)

除 twitter外，在聯邦型分散式社交網路平台 Mastodon 上則是改採 [Mastodon Twitter Crossposter](https://crossposter.masto.donte.com.br/) 服務，來同步到 [Mastodon 帳號](https://g0v.social/@twngo)的推文訊息，取代稍早利用 [IFTTT 同步方式](https://medium.com/@PeiLun/%E8%A8%AD%E5%AE%9A-ifttt-%E5%90%8C%E6%AD%A5-twitter-%E5%88%B0-mastodon-1010ee3798bb)，前者不僅更直覺省心，也能保留原始的 shorten url 資訊。

算一算截至本文寫作為止，共作了 219個 IFTTT applets +　74 個 MS power automate 流程(靠，忍不住佩服自己的無聊，居然可以耐心地重複了數百次無腦不自動動作)。

![IFTTT applets](https://i.imgur.com/IlHCfPW.png)

![Power automate flows](https://i.imgur.com/qLX95SH.png)

#### 正確打開推特的方式 

此帳號在過去三年多來，平均一天推文量約是 21~23 則，隨著外掛越開越多，推文量隨之增多[註1]，恐怕追踪者要有被洗板的心理準備。為了減緩訂閱者的心理壓力和寶貴時間，故推文內容只保留標題和原始連結 url，便於讀者快速地瀏覽一行文標題，若感到好奇再透過url 察看原始全文。 若拒用社交平台者，也可以考慮透過 [Mastodon RSS 訂閱](https://g0v.social/@twngo.rss)功能。

有關這個推特帳號的大小事與過往資料，包括向 twitter 索取的帳號/ twitter analytics 資料大約是每年作一次整理備份，存放在[github](https://github.com/twngo/ngonewstw)。

最後，吾人所整理的[台灣非政府網站資訊列表](https://to.twngo.xyz/lists)，實有不少未竟之處，如有遺漏對象、建議該補充的欄位或是應新增的 NPO 資訊種類，還請有緣看到本文且熱心的朋友提出指正之處。聯絡方式可透過[線上表單提交](https://to.twngo.xyz/addNGO)，或是到 [slack 頻道](https://to.twngo.xyz/slack)裏提出。

[註1] 不知何故， IFTTT 也常會傳回小程式 applet 失敗的訊息，所以並不是每一則 RSS 新訊、 YT 影片、推文都能順利地捕捉進來。