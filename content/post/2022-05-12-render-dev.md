+++
date = "2022-05-12 02:04:00+00:00"
draft = false
title = "render 佈署 hugo"
slug = "render-hugo"
categories = ["internet"]
tags = [
  "github",
  "hugo"
  ]
disable_profile = false
disable_widgets = false
+++

之前利用 hugo 靜態網頁產生器在本地端電腦寫文章後，再把 hugo 轉成的 html 推到 bitbucket 存放發布。但最近一兩年的習慣又變成直接在瀏覽器環境底作筆記。

在 github 推出整合 VSC 網頁版的服務後，動念想是否能直接在 github.dev 直接改碼源庫後自動生成 html 發佈到自己的部落格網站。簡單研究過 hugo 官網的布署說明，但乃不得其門而入。最後是透過 render 靜態網頁佈署的服務，無痛地完成了這件心願。

近來已少碰這些網頁開發工具，所以簡單地作個備忘，以免一兩年後回顧時不記得發生了什麼事

1.  本地端電腦安裝好 hugo , 並下令製作一個新網站:  完成這項動作後,就可以把過去備份在某處的 hugo blog 碼源庫下載回來複制到新網站的資料夾底下。 在該資料夾底下指令 hugo server, 檢查一下網站是否成功地在本地電腦建立

2.  在 github 新增一個碼源庫(repository)，把方才建立的本地端新網站資料一股腦地推到此 repo 

3. 登入 render 在儀表板處新增一個靜態網頁選項，並輸入前一步驟(2) 新建 gitbhub repo 之網址。 記得在設定頁  Build Command 填入 `hugo --gc --minify`  /Publish Directory** 填入 `public` (參見[Render 對於佈署 hugo 的說明](https://render.com/docs/deploy-hugo)

4.  以上 render 就會自動代為把 hugo markdown 檔案改建為 html 並發佈，這裏可以進一步把 Render 提供的網站 url 免費改成[自定域名](https://render.com/docs/configure-other-dns)

5.  之後文章發佈，有兩種方式: 
  1. 第一是先在本地電腦編寫 markdown 文件，再透過 git 推送到 github repo，這已省去了過去得**自己手動**把新的 markdown 文件轉成 html (public 目錄)後，再把 public 底下的 htmls 推到遠端寄存的空間。
	2. 第二個方法是直接在瀏覽器底下輸入 https://github.dev/username/reponame (username/ reponame 為自己的帳戶名稱與碼源庫名) 就會自動替你建立一個 Visual Studio Code 網頁版的編輯環境，它可以直接在瀏覽器執行 git  指令。當 github repo 有變動時，render 定時的檢查服務就會替你把 markdown 文章轉成 html 發佈啦   

![](https://i.imgur.com/OITNucC.png)
