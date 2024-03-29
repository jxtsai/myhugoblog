﻿+++
date = "2017-08-04 17:14:00+00:00"
draft = false
title = "Tails 官網中文推廣翻譯計畫介紹說明"
slug = "about Tails l10n"
categories = ["internet"]
tags = [
  "Tails",
  "l10n",
  "security",
  "encryption",
  "privacy",
  ]
disable_profile = false
disable_widgets = false
+++

最近二個月和一位中國網友（彼此都在 Tails 的本地化郵件群組默默潛水很久，某天對方忽然出聲，果然把我引誘出洞）組成了一個推動 Tails 官網中文翻譯的工作小組。目前總體網站繁體中文初稿已完成了近 80%，但仍然需要不斷有多一支（以上）的新手加入。為了鼓勵迎接更多人可投入此項長期持續工作，稍微整理一下本計畫的翻譯工作流程與相關工具簡介，作為日後工作群組新加入者可參考的上手文件。 
<!--more-->
### Tails 介紹
據說它是一套以強調安全隱私為優先考量的自生作業系統。所謂live system 就是用戶可以透過隨身碟、DVD等方式開機，然後電腦可運行隨身碟、DVD 媒介上的作業系統與其欲載的應用軟體。當電腦關機，抽拔掉隨身碟、DVD後，留存在記憶體上的資料也會跟著消失不留記錄。再者 Tails 的網路接取設計是透過洋䓤的三段式跳接網路，故可保護用戶上網的匿名性。由於其刻意設計的「失憶」（amnesia）、隱身（incognito）、安全開源、自生系統等特色，被視為最佳的安全作業系統之一，據說 Edward Snowden 等網路自由倡議者也是 Tails 的愛用支持者。

我個人約從2015年開始接觸摸索 Tails,，老實說使用它來開機的次數也只是屈指可數的程度而已，倒是狠狠地記得第一次學習它的過程安裝搞得我折損了一支隨身碟，卻依然沒能成功。也許是此一慘痛經驗，讓我深感某些素以資訊安全為優先強調，但其用戶友善度卻大打折扣的網路自由軟體之曲高和寡（喂！），此心理陰影埋下了我今日願意花時間投入其中某些軟體工具的翻譯在地化，希望多少出點力讓這些曲高和寡不易輕近的軟體工具可以再平易一點。當然其中許多曲折的過程，到頭來才會知道即便許多條件的滿足，不一定能促成某些期待的結果必然發生，但那又是另一個故事，暫且不提。

### 參與 Tails 官網中文化專案
工欲善其事必先利其器，因為 Tails 的人有點盯著電腦很久的開發者阿宅性格，目前仍沒利用坊間的翻譯平台（不管是封閉付費的transifex 還是開源的weblate, pootle），要加入其在地化翻譯工作有點小小的門檻－－－就是能略懂 git 指令、以及欠缺人工智能的相似翻譯建議，可耐住性子不厭其煩地重覆好幾次內容相同的翻譯 Orz。想來也許是因為它定位的用戶比較像不願只吃商業軟體餵食的伺料雞，願意動手嘗試古古怪怪開源作業系統的反骨土雞吧。（居然用雞作比喻ㄟ(￣▽￣ㄟ) ）

#### 必備工具：
 - Git - 這是一套代碼版本管理軟體。在各作業平台的安裝以及簡單的指令操作，請參考：[連猴子都得懂的git入門指南](https://backlogtool.com/git-guide/tw/intro/intro1_1.html)或是自行搜尋網路上相關教學資源。 
 - Poedit - 翻譯用的文件編輯器，在各種作業系統平台皆可方便下載安裝
 - OpenSSH client - 要透過終端機加密安全傳輸檔案的軟體。其實如果知道文字指令 git 的操作環境，這個條件也差不多可以算過關了。
 - tools to build a local copy of the website in order to check how it will look like。因為 Tails 官網是透過 ikiwiki 所打造出來，這部份會本文中稍後作介紹。

### 工作流程
#### 1. fork 或下載 Tails 的中文（繁體或簡體）資源庫 
目前，我們已完成近80%的繁體中文資料翻譯，譯者最新的線上資源庫存放在github。要加入本中文在地推廣計畫，可以直接把 Tails 的中文（繁體或簡體）資源庫 fork 到自己的資源庫或是直接下載到本地端，但之後要進行 pull request 可能還是要上傳到某個伺服器端的 git 存放資源。

繁體中文資源庫　@Github  
https://github.com/twngo/tails/

簡體中文資源庫　@Github  
https://github.com/mdrights/tails-zh_CN

#### 2. 本地電腦端工作
建議可以多建立一個分支（嗯，其實我還搞不太懂git branch 的用法），以該分支進行自己的工作，比較不會和他人搞混。 

    git branch translate/contribute ##例如這是我個人依Tails 官網教學，自建了一個名為 translate/contribute 分支
    git checkout translate/contribute ##切換到此分支進行工作

好了，現在可以開始昏天暗地的進行翻譯或初稿校正工作了。主要的網頁文件都是放在 wiki/src/ 底下。目前已完成的[已完成的中文翻譯初稿可參考這份清單](https://github.com/twngo/Tails-zh_TW/wiki/core_to_translate) 。基本上看到 xxxxx.zh_TW.po 就是繁體中文； xxxxx.zh_CN.po 就是簡體中文。如果電腦已安裝 Poedit， 則點擊檔案時，電腦會詢問是否要用Poedit開啟。

![](https://i.imgur.com/7s5yonW.png)

#### 3. Poedit 簡介 
基本上 Poedit 的介面環境，就是左側第二列為「source text」也就是來源文件，基本這一欄的東西沒辦法更改，而主要工作區則是下面的 translation , 請把對應在source text的內容譯成中文。

通常初次登入poedit時，它好像會要求作者得在 ： edit/preferences 填入基本資料。
![](https://i.imgur.com/kHn9OvP.png)

另外在 catalogues/Properties 也會要求在 project name and version,  Team, team's email address, language, Charset  要填入資訊才能成功存檔。

![](https://i.imgur.com/IX3ikto.png)


#### 4. 在電腦的本地端測試
翻譯好的文件是否成功地轉成了網頁 html 
但官網的教學說明只有示範 linux 環境下如何操作，不確定在 windows, Max OSX 如何把 ikiwiki 給裝起來。
如果你幸運的是使用 linux 請在文字指令列輸入：

    sudo apt-get install libyaml-perl libyaml-libyaml-perl po4a \ perlmagick libyaml-syck-perl ikiwiki

這一串指令即是為了安裝 ikiwiki 以及其需用到的相關套件。

安裝完畢後，請將所在的工作目錄，切換到之前進行翻譯的Tails 第一層。基本上只要在文字指令行輸入：

    ./build-website

它就會開始自動把 po 檔案轉換成相應的網頁格式並建立網頁。(不過因為此轉檔過程蠻費時間的，所以建議，可以稍修改該資料夾第一層下 ikiwiki.setup 這支檔案，大約第200行左右的呈現語系選項，讓它僅轉換你要看的語言檔就好)

![](https://i.imgur.com/uAOL35B.png)

當網頁建立好，請利用瀏覽器打開到原工作專案資料夾底下的
config/chroot_local-includes/usr/share/doc/tails/website/

其中有不少從 po 被轉成 html 
![](https://i.imgur.com/CGFprK6.png)

由於 Tails 官網會定期釋出更新版，網站上的訊息也會跟著稍作變動調整，建議最好**一一檢查自己翻譯或校正的網頁**是否能正常顯示，不會發生格式跑掉或內容出現原始代碼的雜亂情形。

#### 5. 校正請求與校稿
- 若有新完成的翻譯文件，請到我們的聊天頻道中 [#localization(zh)@ Mattermost](http://community.internetfreedomfestival.org/) 告之你的資源庫位置，請求他人協助校正。若尚未加入此聊天頻道者，可[email or DM 本人](https://keybase.io/jxtsai)。

- 校正者完成校對後，可以傳送 pull request 給初稿翻譯者，以進行資源庫更新合併。並可同時向直接向 Tails 官方在地工作小組回報修正過文稿的 git repository 資訊，請求將校正後內容放入官網上。

- 當然如果校正者與原譯者對於初稿譯文存有較大看法差距，如何進行部份同意部份拒絕不同意見譯稿的定案以及 Git 版本控制在此方面的協調，我個人也還不太熟此番多人多分支的協作，其實際狀況會是如何。但還是一句老話，有問題就提出來一起找出解決的方法也能多學習到更精進的 Git 的操作技巧。(這個理由一點也不吸引人啊(￣口￣)!!)

工作流程圖
![](https://i.imgur.com/ibUw7Xh.png)

#### 6. 其它資源
持續增補的[英－中重要辭彙表](https://oasis.sandstorm.io/shared/ap4kvm4p60LDBC20hJriYWw69g-gan3IDSn7hMzurfg)

Tails l10n 郵件討論群組（English）:  https://mailman.boum.org/pipermail/tails-l10n/


