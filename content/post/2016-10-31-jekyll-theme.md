+++
date = "2016-10-31 12:09:00+00:00"
draft = false
title = "如何更換jekyll 主題"
slug = "jekyll-theme"
categories = ["blogging"]
tags = [
  "jekyll",
  ]
disable_profile = false
disable_widgets = false
+++
幾個月前，初次接觸「靜態網頁產生器」(static pages generator)，是從jekyll開始才注意到這個東東。接著幾個月中陸續再試玩了hugo, pelican, gitbook, hexo等其它同類型的架站軟體。這一路觀察與體驗下來，雖然使用jekyll來架各式網站或部落格高手最多，其名列了github open sources Static page generator 關注度、使用度最高的第一名，但對於我這名低手幾個月來和它博鬥的經驗總結來說，並不建議沒有任何電腦編程基礎的使用者利用它來作為網站架設的後台工具，理由是：

* 安裝時可能會被ruby的版本以及其套件管理平台gem給搞瘋。
* 就算成功完成了jekyll 在本地端電腦上的安裝運行，但接下來的調校工作，尤其是主題模版更換，很難找得到「新手」看得懂的文件說明。

<!--more-->
對於第一個問題，我在之前記錄jekyll的[部落格文章](http://self.jxtsai.info/2016/04/jekyll.html)簡單地解決了。而這篇文章，則是希望能寫出最平易白話的jekyll更換主題中文介紹,好讓網頁建置或網站佈署有更多元的選擇。至於為什麼目前從google搜尋引擊中，一直沒找到容易看得懂的指引介紹，我個人私自猜測jekyll使用者多是有一定程度的程式碼能力，故他們認為這種理所當然的方法，根本沒什麼做成技術文件的必要吧。

先前提假設,已經通過了ruby/gem安裝考驗，成功地在本機電腦端上裝設好了jekyll。故只要在命令列下新建網站專案指令：
`$jekyll new mysite #mysite為新網站專案名稱，可自取`
電腦即會自動產生一個「mysite」資料夾，其底下有一些必要的檔案與目錄，也就是一個全新的網站。
![](/post/20161031-1.png)

若執行了jekyll 伺服器指令(`mysite$bundle exec jekyll server`)後，打開瀏覧器可看到新網站的模樣，此時套用的是jekyll系統預設的主題：minima
![](/post/20161031-2.png)

接下來同樣在文字指令環境下，打入：
`$jekyll new-theme mynewtheme #mynewtheme為自取的主題名稱`
這時電腦又會自動生成一個「mynewtheme」資料夾，其目錄結構如下：
![](/post/20161031-3.png)

把「mysite」底下的東西全部複製搬移到「mynewtheme」底下，此時在「mynewtheme」的工作目錄下，再打入jekyll 伺服器指令`mysite$bundle exec jekyll server`，這時候會看到一個最原始還未加入任何CSS模版設計與圖片的初胚網站。
![](/post/20161031-4.png)

找到自己看中意的jekyll theme，通常只要搜尋關鍵字，就會有許多豐富的網站，例如我google結果的前三名：
+ [themes.jekyllrc.org](http://themes.jekyllrc.org/)
+ [jekyllthemes.org](http://jekyllthemes.org/)
+ [jekyllthemes.io](https://jekyllthemes.io)

挑選好之後，可以透過：手動下載zip檔案，或是git clone 原始碼到本地端的電腦上。例如我挑選了一個： [Stepbystep主題](http://jekyllthemes.org/themes/Jekyll-Stepbystep/)，下戴其zip檔解壓後，先稍閱讀一下其安裝指南（readme.md）看看有什麼該注意的事項。接下來我是把「Stepbystep」資料夾內的東西全部複製移動到「mynewtheme」。當前工作目錄在「mynewtheme」，利用bundle exec執行jekyll 伺服器命令，沒遇上什麼阻礙順利地讓它跑起來。
![](/post/20161031-5.png)

這時候打開瀏覧器，輸入jekyll本地預設網址http://127.0.0.1:4000 ，耶終於順利更換了jekyll 網站主題。原來更換主題看似也不算太難嘛，那到底之前我東搞西補地探索了兩三個星期是在幹什麼啊(╯-_-)╯ ~╩╩ 
![](/post/20161031-6.jpg)

至於許多細部微調，得要再一一修改_config.yml等檔案。

其它參考資源：
+ [jekyll 官網說明](http://jekyllrb.com/docs/themes/)
+ [一步一步创建Jekyll主题](http://www.jokinkuang.info/2016/09/03/how-to-create-the-jekyll-theme.html)
+ [教你10分鐘內替換Jekyll博客樣式](https://fraserxu.me/2013/06/02/change-jekyll-blog-layout-in-ten-minutes/)
