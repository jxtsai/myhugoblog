+++
date = "2019-09-06 00:04:00+00:00"
draft = false
title = "Hugo + Render + Forestry"
slug = "hugo-and-redner"
categories = ["blogging"]
tags = [
  "hugo",
  "markdown",
  "git",
  "netlify",
  "forestry",
  "render"
  ]
disable_profile = false
disable_widgets = false
+++

[寫過了](https://blog.jxtsai.info/post/hugo-and-forestry/)透過 netlify + forestry 來部署 hugo 並將之化身為透過瀏覽器來管理、協作網站內容的靜態網站管理系統。而這篇文章則要記錄的是另一家與 netlify 類似服務的公司 [Render](https://redner.com)

<!--more-->
Netlify 一度是我個人蠻愛的靜態網站代管服務，但從去年中他們不再為自定域名的免費用戶提供自動 let’s encrypt TSL 安全憑證安裝後 (除非整個域名的 name server 都委由 netlify 代管)。為了避免改更原域名 name server 造成過多 DNS record 也要重新改過的麻煩，自己就鮮少透過 Netlify 佈署網站，改採 github pages 。

[Render](https://render.com/) 是一家相對年輕，與 Netlify 提供類似産品服務的網路商，且免費用戶可自定域名與 https，幾乎是三年前自己剛使用 Netlify 驚豔的翻版，故趕緊來試用看看。可參考一下它的價格方案與對應的服務內容：

![](https://i.imgur.com/kvUqT96.png)

如何使用 Render 來發佈 Hugo，可直接參考 Hugo 官網的[圖文介紹](https://gohugo.io/hosting-and-deployment/hosting-on-render/)，人家已經寫得很清楚了，且操作的確也很直覺和容易，故不再另畫蛇添足。

在完成 Rener 建置後，最後一步，就是來把 Render 系統生成的新網站域名指向自已的自定域名。首先回到自己 DN nameserver 新增一筆 A record, 其映射到 Render 所指定的 IPv4 地址: 216.24.57.1。再來就是新增一筆 cname record, 其子域名 subdomain 看個人喜好，其對映的 hostname，即為原本 Render 提供的新網站域名(ex. hugo-demo.onrender.com.)

完成 DN DNS 新增記錄後，在 Render Dashboard 後台 Settings/Custom Domains， 填入上述設好的 (子)域名，如果沒發生什麼錯誤的話， Render 在完成驗證後即完成了自定域名與 https 的設定，收工。

![](https://i.imgur.com/E1T1oUG.png)
![](https://i.imgur.com/YWUyQTf.png)

如果想再透過 Forestry 來管理、維護這個 hugo repo，則請登入 forestry 再按照之前已演示過的新增站台(Add new site)一步步完成 git repo 的授權串接來安裝線上 CMS，從此就可以輕輕鬆鬆地利用 Forestry 提供的瀏覽器可視即所得環境來編寫網頁內容。

![](https://i.imgur.com/bWVDLu1.png)

目前 Render 免費用戶方案對於靜態網站代管不收費，但如果要使用資料庫、伺服器則價格另計。希望這家新公司能好好順利維持下去，一來別學 Netlify 開太多産品服務線現在都不知如何繼續使用，二來 start-up 別太早燒光資金關門。

