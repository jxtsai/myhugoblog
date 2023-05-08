+++
date = "2023-05-08 11:04:00+00:00"
draft = false
title ="privacyguides.org 正體中文版"
slug = "privacyguides-chinese"
categories = ["internet", "human rights"]
tags = [
  "privacy",
  "security",
  "encryption",
  "digital-tools",
  "github",
  "l10n",
  "privacytools"
  ]
disable_profile = false
disable_widgets = false
+++

今年三年中旬開始在 [crowdin](https://https://crowdin.com/project/privacyguides) 翻譯平台投入 [Privacy Guides](https://privacyguides.org)  正體中文在地化，歷經八週努力終於完成初步工作。

回首 2016年投入[ Privacytools ](https://medium.twngo.xyz/privacytools-io-%E6%AD%A3%E9%AB%94%E4%B8%AD%E6%96%87%E7%89%88-b787b36df994)的翻譯推廣，慢慢在[2021年](https://blog.jxtsai.info/post/privacytools-2021/)燃燼熱情，原本以為再也不必為這個網站傷神 --- 尤其是在 2022 年的某一天重訪 privacytools.io 主站卻發現"人事已非"，也就更能心安理得忘記這回事吧。

然後在今年三月初，原參與 privacytools.io 如今另起爐灶的新團隊成員之一 Daniel 發信給我，簡單地說明新網站的狀況，並提供如何參與在地化翻譯的方式。剛好自己這段時間也閒著，就開始默默一個人作正體中文的翻譯。

![](https://i.imgur.com/Jsa1Li0.png)

除了原始英文版，在 Crowdin 已近乎完成的語言有: 義、繁中、法、荷、西、希伯來語六組，正在穩定輸出的還包括: 俄羅斯語、韓語、印尼語、瑞典語等。不過網站目前所放入的僅四個語系，想來應是最早有志工投入且完成度最高的幾種語言。今年三月起才有人加入的義大利語和繁體中文，在過去兩個月陸續快速地迎頭趕上，希望新語言版本可以很快地被放入官網。 

是說  privacyguides.org 主站利用 [MkDocs](https://www.mkdocs.org/)打造，團隊的開發日誌說，除了直接支援  markdown 語法，使網站文件結構更清楚，便於協作的更新修改，更可以支援多語系的頁面展示轉化。

本次翻譯的工作平台 crowdin，一開始還在摸索熟悉它的介面與流程，作為商用付費平台，其勝出於 transifex 的地方大概是它的機器翻譯引擎(machine translation)除了接合 google translate/ Microsoft Translator，也會根據真實參與者的人工翻譯作建議。所以這次的翻譯過程，自己大部份扮演校閱者角色，確認這些由機器所翻譯的字串，我覺得機器翻譯品質真的是"智能"學習不斷地迭代進步越來越好。而對人腦而言就算只是校閱任務， 還是蠻累心力，但也只有人類有"權力"可以按下確認的確認鍵。

待 privacyguides.org 把正體中文放入官網後，原中文版的 privacytools.twngo.xyz 也會成功身退，我會把 DNS 指向 privacyguides.org。也歡迎各位有心者在 privacyguides 論壇或是加入 crowdin 提出翻譯建議。
