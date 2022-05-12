+++
date = "2017-02-05 14:24:00+00:00"
draft = false
title ="Twitter Profile Analyzer"
slug = "tweets-analyzer"
categories = ["internet"]
tags = [
  "twitter",
  "social media",
  "python",
  "privacy"
  ]
disable_profile = false
disable_widgets = false
+++
之前自己曾照著網路上的教學指南，摸索練習python豐富資源以進行一些簡單的資料抓取分析，例如這篇[python Twython 練習](http://self.jxtsai.info/2016/09/python-twython.html)。因為這一些一點一滴的過程，我才益發真切地感受到，我們每天在（社交）網路上公開的狀態、分享的資訊，除了當事人自以為資訊內容本身欲公開所代表的某種「宣誓、表態、表演」的動作外，這許許多多單一動作本身的發動時間、地點、互動對象、採用工具等等的元數據滙集起來（metadata或稱後設資料，或稱詮釋資料，簡言之，就是活動記錄資料），其實完全不難以拼湊發文者本人的具體個性形貌、政治立場、性傾向....。

<!--more-->
例如在這本「[Network of Control](http://crackedlabs.org/en/networksofcontrol)」(可參考我寫的介紹[Corporate Surveillance, Digital Tracking, Big Data & Privacy](https://blog.jxtsai.info/2016/11/03/corporate-surveillance/)」就透過文獻地爬梳，介紹了現代心理學研究把社會人格類型分成五大類別，這big5簡稱“OCEAN”（openness, conscientiousness, extroversion, agreeableness, neuroticism），而從你個人在社交網站上的活動分析，平均算下來只要收集了68個「按贊」的資料，就可以準確推估你的膚色種族、性傾向偏好、政黨立場、宗教信仰、藥物菸酒使用狀況個人資料等。而這些推估出來的個人樣貌圖譜（profiling），又再放到OCEAN底下，按照這五大類人格特質，投放給當事人符合其個人化偏好的廣告投放資訊、政治行動消息、約會對象推薦等等，以刺激其進行消費、社會行動或下線世界的人際交往。

這些[大數據出神入化的使用](https://motherboard.vice.com/en_us/article/how-our-likes-helped-trump-win)早已不是什麼新鮮事了。我只是一直很納悶：所以這樣的科技世界許諾到底要帶領人類到一個什麼樣的美麗新世界？當個別行為的可預測性早已被機器領先幾步作下了判斷，到底身為一個人的獨特性與存在價值又何在呢？又或者根本就不存在著個體的獨特性與自主這回事吧？

雜亂地扯了一點我個人的困惑，不過眼睜睜地看著許多人拼命用facebook，line,twitter....不亦樂乎地幫忙這些「平台」生產（豐富、優與不優、真與假）內容外，還同時順便奉上個人資料，所以故趕緊拉回原來的主題。本文要介紹用一支以python寫成的程式，可用來簡單地對公開的推特帳號進行分析。據說開發者鑑於第45任美國總統很愛在推特上放炮、碎念所以便做了這麼一支程式，其原始碼可在[github下載](https://github.com/x0rz/tweets_analyzer)。

0.安裝環境：電腦上需裝有python 以及其套件管理pip

1.解壓縮檔案，內容只有5個小檔案，扣除使用說明與版權宣告外，只有2支程式。
![](https://i.imgur.com/pbwv1gi.png)

2.啟動CLI文字指令，當然工作目錄要切到這個推特帳號分析的目錄夾下。在指令列輸入
`pip install -r requirements.txt`
以便利用套件管理工具來安裝此程式所需的4個資源庫。
![](https://i.imgur.com/prjzbVg.png)

![](https://i.imgur.com/f9gJKPw.png)

若要進一步確認是否完整成功安裝所要求的套件包與版本，可在命令列輸入查看
`pip list`

3.修改secrets.py 檔案，填入自己的twitter app api 密鑰資訊。
到[https://apps.twitter.com/](https://apps.twitter.com/) 右上方的「Create New App」,填入簡單資訊，如應用程式名稱、簡單說明、網址等資料後，即可啟用，系統也會回覆Consumer Key (API Key)、Consumer Secret (API Secret)、Access Token等資料。把這資料正確地貼到“secrets.py”裏面相應的位置存檔即可。

4.好了，這樣就可直接利用tweets_analyzer.py 這支程式來對推特上任何一個公開的帳號作分析了。以我想查去年8月底，自己弄的這個[@NGONewsTW 「台灣社運團體訊息推播」帳號](http://self.jxtsai.info/2016/08/ngonewstw.html)只要在文字命令列打入：

` ./tweets_analyzer.py -n @NGONewsTW`

或是

`python tweets_analyer.py -n @NGONewsTW`
(不知為何我按操作指示光輸入`tweets_analyzer.py -n @NGONewsTW`)則會傳回「command not found」的訊息，這好像和電腦安裝python 編譯器的路徑設定有關吧ˇˍˇ）

終端機畫面就會開始去抓 @NGONewsTW最近1000則推文，並作成簡單的分析。
![](https://i.imgur.com/Twpe4a4.png)

這1000則推文的發佈時間分佈，大多集中在每天下午的18~19:00之間。所以推測NGO習慣約是下班前才會把當天的新聞稿或聲明貼到官網上。
![](https://i.imgur.com/ubzu7kG.png)

若以一週為推文發佈分析的基數，則也是明顯地看到，週末訊息量大大減少，多數發佈訊息的時間會落在週間工作日過二到週四，週一與週五則是休假回來的收心與準備要過週末的放心調整期。
![](https://i.imgur.com/REVc0LS.png)

當然，推文的元數據可做資料探堪的材料還很多，包括如果用戶有開啟地理定位資訊，就會知道發推時的經緯度位置，常轉推誰的推文，最常推薦的文章消息來源，使用的發推方式管道等等。
![](https://i.imgur.com/6VA0Hhs.png)

而若在 screen name 後面加入以下某些參數，則會有進一步的功能：

`-h, --help   show this help message and exit`

`-l N, --limit N limit the number of tweets to retreive (default=1000)`

`-n screen_name, --name screen_name target screen_name`

`-f FILTER, --filter FILTER filter by source (ex. -f android will get android tweets only)`

`--no-timezone  removes the timezone auto-adjustment (default is UTC)`

`--utc-offset UTC_OFFSET manually apply a timezone offset (in seconds)`

`--friends  will perform quick friends analysis based on lang and timezone (rate limit = 15 requests)`

#### 後言
有人自為光明正大[無不可告人之處](http://www.ted.com/talks/glenn_greenwald_why_privacy_matters)，恨不得掏心掏肺地在網路上裸奔者,請繼續自便。

如果你意識到在這個數位化大數據時代裏，個人資料居然已經超過自己以為所能自主掌控的範圍，而不甘心就此宿命接受的殘酷現實，除了未來得更小心更清楚地意識到自己是否該在網路上和特定/不特定對象分享交流某些訊息時，總是有個「東西」一直在旁全程記錄。也許必要時候，刪除與遺忘或許才是對自己較適當的方式。

* [Data detox kit](https://theglassroomnyc.org/data-detox/)
* [tweets delete service](https://www.tweetdelete.net/index.php)

