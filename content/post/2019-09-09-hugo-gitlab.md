+++
date = "2019-09-09 02:04:00+00:00"
draft = false
title = "Hugo on Gitlab"
slug = "hugo-and-gitlab"
categories = ["blogging"]
tags = [
  "hugo",
  "markdown",
  "git",
  "forestry",
  ]
disable_profile = false
disable_widgets = false
+++

這是一系列沒什麼實體有料內容，純粹無聊又無處發洩的網誌，要記錄的是如何透過 gitlab CI/CD 自動建置功能來布署 hugo 網站。
<!--more-->

透過 gitlab  與之前介紹過 [Render](https://blog.jxtsai.info/post/hugo-and-render) 代為佈署的最大差異在：後者自動會代為處理 [CICD(Continuous Integration and Deployment)](https://medium.com/@nirespire/what-is-cicd-concepts-in-continuous-integration-and-deployment-4fe3f6625007), 而 gitlab 則要自行新增一支 yml 檔案(.gitlab-ci.yml )，好讓 Gitlab 偵測其指令以執行將相關檔案建置為 html 靜態網頁。
其 yml 內容如下:

```

image: monachus/hugo

variables:
  GIT_SUBMODULE_STRATEGY: recursive

pages:
  script:
  - hugo
  artifacts:
    paths:
    - public
  only:
  - master

```
雖然我根本不懂 CI/CD, 但從這段程式碼大概可以猜出它要依照 hugo  腳本把 markdown 文件轉換成 html, 其存放路徑是 public 資料夾，依據的 repo 分支以 master 來操作。
正因為 CI 連續整合與布署將自動進行 build。這有點像在本地端時下 hugo 指令,即會把變動或新增的 markdown 文件自動轉成 html, 而整個成生的靜態網頁網站即存放 /public/ 之下。換言之這支 yml 檔案的功能即是遠端 repo 內容一旦發生變動，它就會執行 hugo 指令，更新 public 內容後發佈到網站上。也因此在串連本地端 repo 與 gitlab repo 時，記得要在 .gitignore 檔案中要多增一行 /public，讓 git 不必理會本地端 public 資料夾的變動，無須將之推送上遠端 repo。

完成 hugo repo 遠端推送後，gitlab 即會自動偵察到 yml 指令，開始進行 pipelines，如果沒發生什麼錯誤的話，應該可以在```https://userid.gitlab.io/project-name``` (“userid”為 gitlab 帳號，project-name 為該 repo 名稱) 看到寄放在 gitlab 透過其 CICD 服務所建置的 hugo 網站。如果再龜毛一點，想要使用專屬自定域名，gitlab 現在也提供免費代裝 let's encrypt 服務，待完成 txt 記錄驗證後，即可代為自動安裝 TSL。

不習慣(誰呀)使用文字介面者，可以再將此 gitlab repo 串連 forestry.io, 透過 f 站提供的瀏覽器直觀式後台寫作環境來管理內容。不過每當稍變動 forestry 內容傳回 gitlab , CICD 就會花時間執行，感覺蠻浪費電力能源的，這似乎違反當年從 wordpress 改用 hugo 的初衷....

![](https://i.imgur.com/wqn1xTX.png)

