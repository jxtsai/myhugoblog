+++
date = "2019-08-30 00:04:00+00:00"
draft = false
title = "Hugo + Forestry"
slug = "hugo-and-forestry"
categories = ["blogging"]
tags = [
  "hugo",
  "markdown",
  "git",
  "netlify",
  "forestry"
  ]
disable_profile = false
disable_widgets = false
+++

今年寫過二篇如何利用 jekyll + forestry.io , 來打造可以協作的線上網站內容管理平台。自己個人網誌使用的 hugo，雖曾短暫試與之將 forestry 結合，但光在 github 佈署上就撞上不少牆失敗，更別指望能透過 forestry 來作瀏覽器圖形使用操作介面。後來找到一個偷懶的作法: github + netlify + forestry，終於順利解決了 hugo 網頁自動部署的麻煩。本文為簡單地記錄此過程。

<!--more-->
當初在 hugo/ jekyll 之間選取前者作為個人的網誌管理工具，實是因為 hugo 在本地電腦上的安裝要簡易許多。至於它的自動部署設定，則因為我一直沒能看懂其操作文件的說明，查找其它網友分享的經驗也未能解惑，故每次推送代碼更新時，我更新的是下了 hugo 指令後把 MD 文件轉成網頁, 所生成的 html相關檔案(即 /public/ 底下的內容)

根據官網的說法，要利用 git project pages 方式佈署 hugo 有三種方式

1. Deployment of Project Pages from /docs folder on master branch
2. Deployment of Project Pages From Your gh-pages branch
3. Deployment of Project Pages from Your master Branch

第 1 個作法是把原本存放 html 的資料夾(public)改成(docs)，據說是依 github pages 的規矩限制所作的調整。至於第2, 3 種分支操作法，試著按表操課卻仍無法成功，後來看到官網上有提供 netlify 的佈署方式介紹，一試便輕鬆完成。

1. 完成本地電腦端的 hugo 網站製作後，將之整個內容推送上 github 作專案庫代管。
2. 登入 netlify, 新增站台(即右上角深綠底白字" New Site from Git")
3. 挑選好自己存放代碼的 git 管理服務商與 hugo 網站資源庫，授予 netlify 可讀取該 repo 的權限。
![](https://i.imgur.com/vLFSbWd.png)
4. 如果沒發生意外，就會進到以下的操作設定環境, 基本上就按系統預設沒作任何更動，然後就放心地按最下方的"Deploy Site"， netlify 即會代為處理後續的網頁部署發佈動作。
![](https://i.imgur.com/hzQnQeP.png)
![](https://i.imgur.com/Xdw0Xm6.png)
5. 現在網站已 OK 上線了，如果想設定自有網域名，可以在此進行操作。 不過最近二年　netlify 提供了 DNS 服務，使用者必須把自己的域名指向由其name server 代管，它才會代為自動安裝 let's encrypt 憑證，否則就得手動上傳自己的憑證。因主要使用的域名已綁了太多東西，所以挑了一個較少用的域名，又為避免太過拆騰的麻煩，我乾脆把此域名 name server 指向 cloudflare，再利用它提供的免費 TSL 服務，設定指向安全瀏覽的規則即可。
6. 完成透過 netlify 進行 hugo 網站發佈後，接下來則是再透過 forestry.io 來建立線上內容的管理更新。同樣登入 forestry 在主管理畫面右上方"Add Site", 並選擇 hugo 
![](https://i.imgur.com/m4kvhVQ.png)
7. 串接檔案代管的 git 服務商與代碼庫名稱，同意必要的讀取授權。

8. 當 forestry 完成 hugo 網站後台連接後，只須要在" Settings/General "底下輸入此網站的 url，其它無須更動，一切就大功告成。
![](https://i.imgur.com/tKlx7tg.png)

9. 現在可以自由地利用 forestry 來編輯、新增網站文章內容。收工
![](https://i.imgur.com/h5JsrG0.png)

10. 至於其它設置，如增加 template 模版(文章樣式)、設定媒體儲存庫等，在圖形介面環境下使用者不難自行研究摸索。




