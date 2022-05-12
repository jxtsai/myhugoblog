+++
date = "2017-05-12 08:14:00+00:00"
draft = false
title = "hypothes.is 線上註記筆記"
slug = "hypothesis "
categories = ["internet"]
tags = [
  "twngo",
  "digital-tools",
  "hypothesis" 
  ]
disable_profile = false
disable_widgets = false
+++
去年在作[level-up網站中文化](https://self.jxtsai.info/2016/08/level-up.html)時，知道了[hypothes.is](hypothes.is)這個玩意，level-up本身作為一個提供給資訊安全訓練者的教案教學設計指引，本來就希望其網頁資料能方便使用者（資安訓練講師）能透過各種安全又方便的回饋管道與方式，來收集各方意見改進其教材。

最近因為打算要作個小專案網站，再次想起了 hypothesis，剛好趁此好好了解它的使用順便寫下一點簡單的介紹教學。
<!--more-->

開用前，得先在瀏覽器端進行一點前置準備。目前 hypothesis 提供了四種方式可讓用戶在任何（表網明網）網頁上使用這個線上筆記註記工具。

#### 安裝hypothesis
1. 安裝Chrome瀏覽器延伸外掛，這應是最簡單的作法。不過一開始因為Chrome並不是我最常用的瀏覽器，而火狐、Brave、Opera 等又沒這支hypothesis 延伸外掛，不免有點失望，難怪我之前這麼久都沒能好好理解hypothesis的使用方法。這幾天仔細看了官網的使用說明，才知道還有其它方式可以讓 Non-Chrome 瀏覽器也可「輕鬆地」使用。
2. 無外掛的其它瀏覽器可利用hypothes.is　首頁提供的“bookmarklet”棕紅色按鍵，把它拖曳拉到瀏覽器的書籤列，日後在此瀏覽器看到任何想留下個人筆記注解的網頁，只要到書籤下啟動「launch hypothesis」，這個指定的網頁左側即會自動出現hypothesis工具欄。(註：只會出現在用戶個人的瀏覽器端，如果別人本身沒使用任何hypothesis，在他自己的瀏覽器是不會看到hypothesis的。這和在Chrome瀏覽器下安裝延伸外掛是差不多的原理）
![](https://i.imgur.com/PNK4jTx.png)
![](https://i.imgur.com/yNLQ9Wr.png)

3. 利用　hypothes.is　首頁的"post a link"輸入區，貼上想要作筆記的網頁，則它會自動在你的瀏覽器端幫這個指定的網址加上hypothesis工具列

4. 網頁作者主動在自己的網站上安裝　hypothesis , 如同一開始就提到level-up.cc的作法。而這個作法與前三項最大的不同在於，前三者因為網站本身未安裝 hypothesis，故安裝後只會出現在自己電腦瀏覽器，但最後一個方式則是網頁伺服器上也有了 hypothesis，故任何瀏覽 level-up.cc 的訪客都可以看到 hypothesis工具欄隱隱安靜地出現在左側，用戶不必再透過前三種方式近用hypothesis。

瀏覽器端安裝好後，接來下則是
#### hypothesis使用介紹 

1. 在官網上註冊帳號，登入後即可開始在自己電腦的瀏覽器上使用。
2. 當瀏覽器啟動 hypothesis 後（左側出現hypothesis工具欄），則當用戶使用滑鼠反黑網頁中的文字時，就會頁面處自動出現一個小工具顯示"annotate", "highlight" 前者註記功能（也就是左側浮動工具欄那個小筆記本的圖示），後者是將文字高亮顯示（大眼球圖示）
![](https://i.imgur.com/waMPi0r.png)
3. hypothesis 除了讓用戶可以決定，其網頁筆記注記是否要公開或自己看看就好，另外還有設立群組（group）功能。換言之，個人的筆記也可以丢入自己所屬的社群來和某一群共同興趣者交流交換。新設群組的方法只要在其工具欄出現後的"Public"下方"+ New group"即可。目前看起來，hypothesis group 的加入方式，不是自己創一個後邀請別人，就是受到別人邀請後加入。hypothesis 官網上並沒有什麼公開群組列表。

4. hypothesis 目前能支援的，是在瀏覽器底下使用 HTTP/HTTPS/FTP 三種協議的網頁，因此也可以支援以瀏覽器讀取的pdf文檔。
5. [Stream](https://hypothes.is/stream) 有點類似社交網站上的时間流，而在hypothesis則是用戶願把自己的筆記註記作公開分享發佈的串流。

官網上的介紹短片
[![Hypothes.is Animated Intro](https://img.youtube.com/vi/QCkm0lL-6lc/0.jpg)](https://www.youtube.com/watch?v=QCkm0lL-6lc)

#### 後記：
1. 印象中坊間似乎有不少商業軟體或營利平台有提供類似的網路註解或筆記等功能工具，例如我這一兩年比較常用的[diigo](http://www.teachers.fju.edu.tw/epapers/index.php?option=com_content&task=view&id=325)。不過對於我這種稍有開源自由軟體情結的使用者，hypothesis以非營利的姿態和標舉著[12大原則](https://hypothes.is/principles/)，更能贏得我的青睞。

2. 最來常在火狐瀏覽器下欲使用 hypothesis，卻發生“Session invalid”無法登入的訊息。根據官網上解釋，這是因為目前hypothesis需要用戶同意使用第三方的 cookies 才能使用，如果用戶在瀏覽器安裝一些隱私強化的延伸套件,可能會阻檔了cookies小程式，造成無法登入的狀態。雖然官方宣稱未來版本會改善不再透由第三方的 cookies，不知道這還要多久的時間。




