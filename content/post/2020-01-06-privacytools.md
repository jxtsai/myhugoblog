+++
date = "2020-01-06 02:04:00+00:00"
draft = false
title = "Privacytools 網路隱私工具 2020 改版登場"
slug = "privacytools-2020-updated"
categories = ["internet"]
tags = [
  "privacy",
  "privacytools",
  "netlify",
  "open sources",
  "l10n"
  ]
disable_profile = false
disable_widgets = false
+++
自從 2016 年年底[第一次發佈 Privacytools 網路隱私工具中文版翻譯](https://to.twngo.xyz/12272016)，沒想到有一天它卻慢慢變成自己尾大不掉無法攞脫的惡夢。尤其是兩三個月前，重讀一年前自己在[第二次中文化改版寫下的文章](https://to.twngo.xyz/01222019)，真是不知道當時哪裏來的勇氣和口氣…..Orz

<!--more-->

老實說，到了第三年，還是只有一個人在橕這個網站的中文資訊維護，大概只證明自己的失敗吧。所以這回在默默整理新版資料的過程中，真的不是很開心，有點後悔當初為何一頭熱作這件事，三年後的今天則充斥著拔劍四顧心茫然的無奈。

既然作得不開心，不情不願下為什麼還要再投入第三次改版呢？我想原因可能是：自己抖 M 的受虐體質(活該，攤手….)。作為一個算是重度的網路使用者（雖然不常使用社交軟體和手機），大概知道一點數位安全的技術漏洞與人心易被影響的脆弱後，總覺得既然是自己啟頭似乎有點道義上的責任要對中文網站的訪問者負責，自己背的鍋也只能跪著把它背完。

傾倒一點個人垃圾後，還是回歸正題，簡單說明一下本次改版作了哪些事。


### privactytools 免稅資格登記與服務提供隨之新增內容 

如果從 2016 開始注意　第三次的最大更新改版，主要是配合英文網站從 2019 年中開始新增了多項免費安全的網路服務(如 discourse 論壇、matrix 聊天室、Mastodon、個人部落格寫作寄居…..)，以及 privacytools 依美國向 IRS 填表登記成為可享捐款扣稅的非營利組織地位優惠(Open Collective Foundation 501(c)(3))。 隨著網站團隊日益"建製化、組織化"，在主網頁新增了捐款資訊、贊助招募以及團隊介紹等資料，鑑於中文用戶可能對此類資訊的興趣很低，所以未予翻譯。

而在主體內容關於各式軟體或應用服務部份，最大的變動是已有的 VPN、DNS，新增了社交訊息聚合(俗稱的網路佈告欄)，以及對於當紅的加密即時聊天通訊再進一步按 server/instance　類型作了基礎的優劣比較。VPN 與供應商資訊頁，較前版補充不少 VPN 使用迷思，對大部份網民對 VPN 一知半解的認識應該有新啟發。至於 DNS 部份， DNS 在整個網路瀏覽過程裏其重要性與被理解被看到之間失衡的不對襯，的確值得更詳細的介紹。

### jekyll 

前一次大改版主要是 privacytools 從純 html 手工，改採 jekyll 為網站建造架構，但所有的頁面仍是 html 語法而不是簡潔的 markdown。有興趣查看源代碼，可以自 [github](https://github.com/twngo/privacytools-zh)下載整個 repo　後安裝 ruby/gem 以及需用到的依賴封件包後，在本地端電腦激活生成的靜態網頁網站。除卻版型、樣板格式、圖片等組合網頁的骨骼積木外，實質血肉內容主要放在 _includes,pages 二個資料夾底下。這回再作更新，越堆越多 html 語法標籤或是由 { } 包起來的 html 模版，造成譯者從數十份文件找出需要翻譯部份的不便，例如有些包在 < >裏的資訊，雖未直接呈現在網頁上，但如鼠標移置到該處，則會出一段文字說明(目前未翻)。又或者有些小地方不容易注意而造成輕微的排版瑕疵，請容我有空再慢慢改正。

猜想在 html, template 作中文化手工，再透由 github 維護更新的作業手續，對絕大多數網民讀者就算想幫忙參一角協助也是力不從心。或許透過更直觀的翻譯工作平台，如 transifex, weblate 能更隆低參與的門檻。有位大大利用 weblate架了一個[privacytools 翻譯工作站](https://weblate.nablahost.com/projects/privacytoolsio/)，希望有一天前端中文化的工作可以移轉到哪裏進行。

### CI/CD + Netlify

據說使用 jekyll 的好處之一，是如果懂 [CI/CD, aka “continuous deployment”](https://en.wikipedia.org/wiki/CI/CD) ，則可以把本地端整個 jekyll 網站資料夾寄存在 github/ gitlab，當開發者 push 變動時，repo 就會自動更新 gitpages 靜態頁，不用把生成的靜態頁面檔案(_site) 另外再弄一個 repo 。對，沒錯，因為我到現在還不會設定 CI/CD 所以就是得在自己電腦的本地端先手動產生最新的網頁資料，再將這個網頁資料檔案夾(_site)的內容推送到 github/gitlab 另一個不同於 privacytools-zh 的 repo 。今年本來想學習一下 CI/CD 要怎麼弄，但過程並不順利，後來想起原本即透過 netlify 為中介來發佈 privacytools 中文版，當初是圖 netlify 可自定域名還可以代設 let’s encrypt。但當 gitlab/github 去年起陸續為自定域名的 gitpages 提供 https， Netlify 則反其道地開始要求使用者必須將 Domain Name Server 設成他家提供的伺服器才能用 https，多少讓我對 Netlify 已心灰意冷（幸而 2019 年之前已完成自定域名的網站仍可繼續使用自動延長的 STL，故 privacytools 中文版的 cname 一直綁在 netlify）。這回想到正好可以讓 Netlify 自動代勞處理佈署，一路順利地把 jekyll + CI/CD 弄好，日後 jekyll 主支更新即會自動生成靜態網頁並佈署到發佈。（有人可以教我 netlify＋Hugo 及 gitlab + Jekyll 自動布署嗎。目前試只成功 netlify＋jeykll, [gitlab+Hugo](https://blog.jxtsai.info/post/hugo-and-gitlab/)，但另兩種組合卻一直失敗…）

以上。好啦，反正這個自己愛寫什麼就亂寫什麼的私人部落格裏，就是盡量誠實地記下出這些自我厭惡、懷疑、碎念的負能量，看看一年後心情會轉到哪裏。

我們 2021 再見？