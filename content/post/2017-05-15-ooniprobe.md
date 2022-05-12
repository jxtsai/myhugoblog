+++
date = "2017-05-15 13:14:00+00:00"
draft = false
title = "OONIprobe/ M-lab 在地中文化翻釋"
slug = "ooniprobe "
categories = ["internet"]
tags = [
  "surveillance",
  "OONI",
  "l10n",
  "Tor"
  ]
disable_profile = false
disable_widgets = false
+++
這兩三週翻譯了二個小東西，一個是TOR 計畫底下的一支專案：[OONIProbe](https://ooni.torproject.org/),它是一個偵察測量用戶所在的互聯網自治區內（AS, Autonomous System）是否存在著網路審查與流量監控的記錄工具。另一個是[M-Lab](https://www.measurementlab.net/)欲讓一般網路用戶安裝在其Chrome瀏覽器的延伸套件，以助其收集全球網路連線的健康狀態數據。 

<!--more-->
大概是去年底偶而看到[OONI, Open Observatory of Network Interference](https://ooni.torproject.org/)，剛好我對網路審查與數位監控感到很好奇但又不知道到底相關技術是如何可能、如何進行。但當時只是簡單地查了一下台灣的數據，沒認真了解它的研究方法。最近想來還清除一點人情債，就決定翻譯 M-Lab Chrome Extension / ONNI 這二個工具。作為一名技術白丁，再怎麼讀網路概要101教科書，我還是看不懂絕大多數的技術文件，最笨的方法，就是剛好借由一些網頁式、手機應用程式專案的關鍵字串翻譯，多少幫助我了解一點到底網路審查是透過何種方式進行的入門知識，一方面也可以順便把相關的資訊資料中文化，或可讓更多人了解互聯網一些基礎協議設施與數位人權的問題。 

### ONNI(Open Observatory of Network Interference) 
ONNIProbe 這個工具除了電腦版外，還有智慧型手機（Android / iOS）可安裝的應用程式，在手機上用戶只要透過google play 商店或在安卓系統自由開源的程式區F-Droid下載安裝，即可開始使用。

#### 手機版畫面 

![](https://i.imgur.com/IGeoeJP.png)
![](https://i.imgur.com/wdeFbdY.png)
![](https://i.imgur.com/Oi09xL7.png)

雖然還是看不懂有些測試結果報告上所代表的意義（例如 NDT 所作的網路速度測試，這樣的數據表現到底是「好」還是「不好」）。老實說，在台灣玩這種東西好像還蠻無聊的，看不出什麼端倪（不知道在台灣中小學學術網路測試會不會出現一些比較有趣的狀況）。

#### 電腦版
除了人人皆可無痛下載安裝的手機版外，ONNIPROBE還可安裝在電腦上（以Unix為架構發展出的OSX / Linux）。我使用的作業系統是ubuntu 14.04, 從官網的安裝指示原以為很簡單，但是安裝好欲啟動執行，卻傳回有幾支程式需要的pythonk套件集欠缺，無法成功執行。為了補齊套件就費了不少力氣，幸而最後還是順利把它運行起來。

![](https://i.imgur.com/Ull0m8k.png)

在文字指列下執行這行指令： $ooniprobe -w 
(-w 指的是啟動網頁瀏覽器介面)
網頁瀏覽器就會自動開啟它的網址，一般應是http://localhost:8842/

![](https://i.imgur.com/SfdiQLV.png)

![](https://i.imgur.com/lOJaaou.png)


### M-Lab 
除了ONNIprobe 主要的功用是透過一些網路協議技術，如HTTP Invalid Request Line、 DNS、 TCP/IP等方式(我現在只知道其名，但還是不完全了解其可進行審查封鎖資訊的運作原理)進行網站是否可能封鎖的測試外，也結合了[M-Lab](https://measurementlab.net)的NDT (Network Diagnostic Test)功能來檢查用戶所在網路區Autonomous System 的連線速度與健康表現。M-Lab推出一套可安裝在Chrome瀏覽器的延申套件，一方面可以讓用戶以此測量其「網速」,也請求用戶同意把這些數據回傳給M-Lab，好讓他們盡可能地收集到全球網路的連線，是否有斷線或流量異常等狀況。

![](https://i.imgur.com/DPhmu0P.png)

![](https://i.imgur.com/70W8oQK.png)

這些算是「眾籌」的網路狀況資料，可公開在M-Lab網站找到，它還利用此數據集作了簡單的視覺化圖表。
![](https://i.imgur.com/WaBCOm1.png)


#### 後話

如果從OONI所收集的數據上來看，[台灣的網路](https://explorer.ooni.torproject.org/country/TW)環境中並沒有存在「不適當」的網路審查與網站封鎖。言論自由，可能是過去20多年淺層的民主化改革過程中，留給台灣社會最重要的價值資產之一。但思想與言論自由除了直覺、傳統上不希望國家或它人介入干擾個人的自由意志思考與表達出來的權利外（先不論表達內容是否符合「言論自由」權利有限制的保護標的）；其實也有著**個人是否能自由地、不被限制地追求取得自己欲了解某些資訊的知情權利**。過去威權政體透過恐怖統治與媒體管制，壓抑了人民自由思考與發言的機會，而在互聯網大幅降低發聲門檻後，對於網路發動言論審查，則傷害和侵犯了人人追求事實與探查真相之權利。

在數位化網路科技的台灣，面臨的捍衛言論自由之戰，或許不是像中國、俄羅斯那樣“開明”獨裁者仍然明目張瞻地以捍衛國家安全、民族尊嚴和網路主權等說法，透過技術工具的協助來控制網路上流通的資訊。然而權力資源掌控者（不只是政府，可能也有不想被問責的大企業老闆....）聰明地進化，就是繼續讓當前最重要的資訊交換媒介－－互網聯以及其它媒體廣播電台、電視（新聞）台、報紙，都充斥著過多無關緊要、不痛不癢、轉移焦點的垃圾資訊，進而淹沒壓擠了消費者（公眾）的專注力。

作為一個理應要追求知識成長與資訊滿足的自由人，在這個內容農場資訊過份供應、鄉民正義充斥的年代裏，又該怎麼去應對權力者不斷釋出粗裂資訊的干擾雜訊呢？ 這大概是無國界記者協會評比亞洲新聞自由度最高的台灣，本地聽閱者、資訊吸收者、報導者、新聞工作者，時時刻刻戰戰兢兢得不斷自問的課題吧。

其它值得一讀：
[中國的審查制度是如何運行的](http://www.chinagfw.org/2017/05/blog-post_13.html)（艾未未）

[20170514 台灣 政府服務網路 著手封鎖公開的 DNS 主機 Google DNS](http://www.metamuse.net/2017/05/dns-google-dns.html)
 

