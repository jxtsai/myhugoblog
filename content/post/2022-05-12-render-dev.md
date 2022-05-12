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

在 github 推出整合 VSC 網頁版的服務後，動念想是否能直接在 github.dev 直接改碼源庫後自動生成 html 發佈到自己的部落格網站。簡單研究過 hugo 官網的布署說明，但乃不得其門而入。最後是透過 render 靜態網頁佈署的服務完成了這項任務。

Render 對於佈署 hugo 的說明 
https://render.com/docs/deploy-hugo

這樣以後就可以直接在 https://github.dev/jxtsai/myhugoblog 的瀏覽器環境下寫文章後自動發佈到個人網站

(尚未設好自定域名)