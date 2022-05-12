本站隱私聲明
============

既然多多少少寫了一點關於數位隱私與個人資料收集的議題，我想自己也得該負責任地說明一下這個網站的隱私權政策。

日前透過EFF(Electronic Frontier Foundation)開發維護的瀏覧器附加元件privacy badger 才知道部落格底下有幾個自己原本也不知道的其它網站cookies與追踪器，可能會收集瀏覧本站訪客的資料。
<!--more-->

![](https://i.imgur.com/elEjh3b.png)

後來我查了一下原始碼，這幾個網站分別是：

* cdnjs.cloudflare.com　hugo 原始碼中用來執行Jquery程式存放空間，也因此被放入了追踪器。

* mathJax.org: hugo 原始碼中為了支援數學式語法，用了這個網站的javascript，連帶也被放入了其cookies

* fonts.googleapis.com hugo採用了某些網路字型支援，目前依privacy badger的診斷，尚屬健康狀態，並未裝追踪器。

* disquis.com 因為hugo或大多數的靜態網頁生成器本身沒有評論或留言功能，多得靠第三方外掛來補強此不足,所以在單篇文章的讀取頁面上，會發現多出了好幾個disquis.com名下的追踪器或是cookies。其實也一度思考，到底是否還有必要保留留言功能，除了本站瀏覧數本身就少外，會願意留言交流者更是少之又少。不過對我自己而言，若有什麼相關的資訊，透過留言區作補充而不必動更到內文，其實比較方便，所以姑且先保留下來吧。

* 另外原本之前一度安裝google analystics ，但實在不想再過度依賴與相信這家公司，所以曾經試著改用piwik這個開源的網站流量統計分析工具。當時是把它安裝在sandstorm 平台上，但不知哪出了錯，一直沒法追踪到𥢜本站的程式碼數據，所以乾脆就放棄了。讀者如果在單篇文章頁面，則會發現有google analystics，我猜可能是disquis所放入。


最後，感謝EFF開發了[privacy badger這套工具](https://www.eff.org/privacybadger), 請多加擅用，若有餘力請出錢支持EFF繼續捍衛數位人權。

![privacy badger](https://www.eff.org/sites/all/themes/badger/badger-stroke.png)
