+++
date = "2016-11-15 17:14:00+00:00"
draft = false
title = "（安全）網路使用工具清單-桌機筆電篇"
slug = "digital-security-tools"
categories = ["internet"]
tags = [
  "surveillance",
  "privacy",
  "security"
  ]
disable_profile = false
disable_widgets = false
+++
11月9日過後的幾天裏，我的推特圈上最充斥的是：一些美國人權組織發表募款訊息號召更多會員加入以準備對抗2017年１月之後所將面臨的長期抵抗。除此之外，不少教新聞記者、人權工作者以及內部吹哨者（whistleblower）如何加強自保以及強化通訊私密數位安全交戰手冊等，也再一次被拿出來推廣。

看這些消息被轉來轉去之際，我想自己過去一年多來也親身體驗了不少數位資訊安全的工具、逃離獨大壟斷集中式商業軟體或「免費」服務對個別用戶的資枓與習慣綁架與依賴，分散減少數位安全風險，而在台灣中文社群中似乎較少看到這樣的資料整理，故先野人獻曝一下地分享我較常使用的「另類」（數位安全）網路使用工具清單，本文先以個人電腦、筆電為主，稍後再整理智慧型手機：
<!--more-->
#### OS作業系統
linux ： 目前使用的是以debian為基礎的ubuntu, linux mint, Tails(隨身碟用)。
#### VPN
因為沒錢用付費的VPN，若有需要偶而會利用hoxx 等免費VPN網路服務來瀏網。
另外有一套免費的Hamachi，則是可以讓使用者建置自己的虛擬區域網路，不過這工具對我不太實用。
#### 瀏覧器
還是習慣firefox囉，尤其要補充上一些安全外掛。
![](/post/20161115-1.png)

但如果要造訪darknet,那就得用tor瀏覧器（我當然是沒那麼黑地要經常造訪什麼深網、暗網）。
另外也推薦另一款跨平台的開源[瀏覧器brave](https://brave.com/)，我會安裝它的原因是，其團隊看起來很酷，CEO是mozilla的共同創辦人，而其工程師裏也有不少人參與了TOR開發社群。
### email 服務
* [protonmail](https://protonmail.com) 主機位於瑞士的加密郵件服務，免費版提供500MB空間。付費版的話，年費為48歐元，可自定網域名。
* [tutanota mail](https://tutanona.com)主機放在德國,免費版提供1G空間，付費版年費是12歐元,並可自定網域名。
以上這兩個免費的內鍵加密功能電郵服務，所以在你撰寫郵件時，會詢問是否要對該郵件進行加密處理，而收件人則要另外透過其它管道知道解密的密碼才能順利開啟信件內容。
![](/post/20161115-2.png)
![](/post/20161115-3.png)

* riseup.net #我沒使用，不過好像蠻多人權組織都蠻推薦的，其服務為免費，但專門保留提供給（數位安全）高風險工作者，要用人工申請方式取得帳號。

當然最佳的安全作法就是：**不要把信件「永久地」**保留在webmail server上，否則yahoo, gmail, microsoft等免費郵件𦃝網路供應商會利用機器來「讀取」信件（他們會說這不是「人」來讀取，所以沒有侵害隱私問題）以便提供對用戶最適化的「量身」服務內容。就算你個人不會對機器讀取信件內容的安排感到不適，想想這一年來大大小小的郵電門醜聞或是大量帳號密碼被駭的資安事件，還是定期刪除留在（他人）伺服器上的郵件，免得有一天自己都忘了的陳年舊帳被別人翻出來作為算計對付你的籌碼。
故我另外再利用自己專屬網域，由廉價主機商ipage.com提供郵件伺服器設定了一個個人電郵，但想必其伺服器與傳送過程絕對是可以被任意攔截毫無安全隱私可言，所以利用這組電郵地址作了一組[PGP密鑰](http://self.jxtsai.info/2005/03/this-site.html)，搭配郵件軟體thunderbird enigmail外掛，可用於加密郵件或訊息接收。
#### social media
* 我個人刪除停用臉書大約有4、5年了，當然多少會覺得沒法「了解」、「參與」「正在發生」的熱門消息有些許遺憾，讓他人覺得不好相處不知怎麼與之「社交」的冷僻感,這我也沒辦法（攤手）（ノ＿　＿）ノ▽
* twitter之於我而言，大量程度用來替代12~13年前透過RSS訂閱各種個人blogger、新聞、組織消息的快速捷徑管道,對我來講它應該不是什麼「社交媒體」吧（還是我根本就是反社會人格啊？）。幸好目前它還沒有讓人討厭的(臉書)過濾演算法（吧？） 從2015年起，我慢慢改用[quitter.se](http://self.jxtsai.info/2015/04/blog-post_20.html),分散式GNU social當中的一個「邦聯」（federation)，來作140字元以下的書籤或沒份量的雜感抒發。如果有一天twitter被某家我所討厭的巨獸企業收購，除了靜靜哀悼它的死去外，對我個人衝擊大概就是得回頭重新利用電子郵件newsletter/ RSS Feeder訂閱訊息管道吧。
* 部落格/個人網站：長篇文章的撰寫（現階段主要為了自己參考用的個人筆記分享），還是得把儘可能主控權拉回來能自己掌握。目前本站是使用[hugo建置](http://self.jxtsai.info/2016/07/hugo.html)，佈署在github pages上面。（但瀏覧器在網址列url打入https：// 會出現很醜的不安全紅字，讓我一整個很想搬到gitlab佈置在netlify，因為他們提供的是let's encrypt）

#### search enginee 搜尋引擊
重視隱私者會推薦的是[Duckduckgo](https://duckduckgo.com), 雖然我曾一度試著利用它，但其搜尋結讓我不甚滿意。這兩天重新再看一遍Tactical Technology Collective 好幾年製作的網站[Take control of your data](https://myshadow.org/),其上推薦的其它替代google搜尋引擊有：
* [Searx](https://www.searx.me/)
* [StartPage](https://www.startpage.com/)
現在改用startPage(Ixquick),感覺其搜尋結果似乎與google差不多，據說是建構在goole上的搜尋服務，但startpage宣稱，它們不會記錄用戶的IP地址與搜尋辭字，網站上也沒有任何cookies 或追踪器，（不知這樣是否會被google提告侵權啊），姑且先相信它來使用看看。
#### 文件試算表線上編輯
之前一度常用hackpad, 現在則多改用 hackmd.io,或者是自己建在sandstorm上面的ehterpad。偶而還是會使用google drive,尤其是先透過它們來開啟一些文件檔案確認沒什麼病毒惡意軟體問題再下載到電腦。
#### VOIP網路電話視訊
因為近來並不太常用網路訊視,大量減少了對skype or google hangout的使用依賴,如果有必要則是配合他人使用Jitsi,所以麻煩不大。
#### 線上聊天室
現在反而覺得20年前就出現的IRC線上聊天協議已差不多已夠我使用，長時間掛在某聊天室中，偶有某種回到小時候在客廳巷口廟埕聽大人或三姑六婆聊天下大事與八卦之感。如果要花俏一點的網頁版，不妨試試[riot.im](http://self.jxtsai.info/2016/09/2-riot.html),另一款分散型的開源聊天工具。之前也寫過slack替代開源工具[mattermost](http://self.jxtsai.info/2016/08/mattermost.html), [rocket.cafe](http://self.jxtsai.info/2016/08/rocketchat.html), 或是與riot.im 係出同門的matrix(又稱[synpase](http://self.jxtsai.info/2016/09/3-synapse.html)),這些都可作為「極度」重視隱私與資料自主控制者而又得須要協同工具平台聊天環境者自行架設其服務。

#### 雲端儲存空間
這部份自己另類工具的實踐最差，主要還是依賴dropbox/ box，唯一的可作的強化安全措施似乎只有再上傳到雲端之前，先把[重要的資料作加密處理](http://blog.jxtsai.info/2016/10/28/file-encrypt/)。

#### 數位安全相關參考資源：
* https://privacytools.io
* https://securityinabox.org/
* https://riseup.net/en/security
* https://ssd.eff.org/en
