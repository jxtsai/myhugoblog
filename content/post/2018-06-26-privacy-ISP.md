﻿+++
date = "2018-06-25 10:34:00+00:00"
draft = false
title = "網路隱私、個人資料與 ISP(上)"
slug = "Online-Privacy-and-ISPs-1"
categories = ["internet"]
tags = [
  "business surveillance",
  "privacy",
  "big data",
  "data protecion"
  ]
disable_profile = false
disable_widgets = false
+++
作為一名長期的網際網路 internet 愛用者，即便曾協助作過一點點網路自由（對抗言論審查封鎖或是加密、提高使用者隱私等）工具軟體與相關資訊的中文翻譯推介，但是過去一年自己才更有意識地懷疑於到底我的哪些「個人資料」，如何在我使用網際網路時上被（哪些人）收集、處理，甚致是更進一步地在我未明確知悉與授權的狀況下，「轉售」或提供給哪些第三方來其它目的的使用。

為了追究上述個人的小小疑問，最近試圖著系統化地作點功課，並將這樣的資訊記錄下來。想像也許某一天，向來自認一生坦蕩蕩每天在網路上公開三餐吃什麼的過路人看到這樣的個人資訊在網路上裸奔流竄的現實後，會重新好好想想在數位時代中個人資訊曝露程度與保護段是否要再調整。

<!--more-->

如果讀者從未知覺到提供接取網際網路資源的 ISP 可以知道關於你的何種資訊，不妨先試著點擊打開這個網址 [Protect your Privacy from your ISP with Private Internet Access](https://www.privateinternetaccess.com/pages/privacy-from-internet-service-provider-isp)，看看頁面右側欄顯示出哪些此刻關於你的資訊：當前地理位置、IP、瀏覽器資訊、作業系統。除此之外，每每當你的瀏覽器欲開啟某個 url，則得先透過 ISP 提供的 DNS  解析功能，還原此 URL 伺服器的 IP 資訊。換言之你的瀏覽器造訪了哪些網站，什麼時段訪問，讀取什麼內容，停留多久時間....ISP通通一目了然，更別提你在申請 ISP 服務帳號時必須提供的個人身份、聯絡方式、付款資料等等。（此處先假設訪問的網站未有 HTTPS, 未設定其它 DNS 服務，未使用VPN/Proxy）

**參考資料：[互聯網：網路個人資料可視狀況總覧 ](https://blog.jxtsai.info/2016/11/09/5wofinformationonline/)**

稍微認真地翻讀了下2016年由美國 Georgia Tech 喬治亞理工學院 Peter Swire 教授等人所發表的「[Online Privacy and ISPs](https://www.privateinternetaccess.com/pages/privacy-from-internet-service-provider-isp)」安全隱私系列研究文件。

這份文件的重點不在其題目反而是其子標題-----ISP Access to Consumer Data is Limited and Often Less than Access by Others。先補充一下此文件發佈的時空背景，當時美國 Federation Communication Commission 在前一年通過多數決，將 ISP 列為電信法中規定的第二類公共承運人或公共通訊企業（ common carriers under Title II），若被歸類為第二類公共承運人，則表示 ISP 須要擔負更高的公共責任，其中也涉及了對用戶隱私與資料保護上的責任密度加重[註1]。故作者群在報告中反覆強調，此研究是立於技術事實基礎的推論與建議，而不是為了討好哪一個政治黨派。

根據 Swire 等人的研究，他們認為因技術的開發改進以及上網工具與習性的變化，今日 ISP 能夠監控掌握用戶網路活動內容的能力已大幅受到限制，進一步說明如下：

1. 90年代，用戶上網可能是家中唯一一台桌上型電腦（多人共用）連上某家固網式 ISP 開始沖網。但在今天，一名用戶平均有6.1套上網設備，其中多數是行動裝置，使用不同的電信業者上網數據方案或在不同的空間地點裏使用不同家的 ISP 服務。另一方面，行動數據流量有近半數是透過無線 wifi 上網。換言之，今日 ISP 僅在用戶上網流量中提供一部份有限的連網服務。

2. 無所不在的加密技術應用，例如瀏覽器網頁基礎通訊協定改採多一層加密的 HTTPS，主流瀏覽器如 Chrome, Firefox 過去三四年來強力推廣 secure by default，促使了網站管理者紛紛改採加密連線的安全預設。網站 HTTPS 使用比例大幅提高，也相對地降低了 ISP 知道用戶連線到某些網站讀取什麼內容的透明可見度。

3. 網際網路協議基礎設計中的 DNS 查尋，讓 ISP 可以知道用戶試圖連上哪一個網域，通過 url　的資訊記錄來掌握用戶的上網活動。除了之前所說的 HTTPS 讓 ISP　僅能知道用戶請求接取某個 DN 域名伺服器，但並無法知道用戶在該 DN　底下的詳細具體活動狀況。再者，如果用戶進一步使用了 VPN (Virtual Private Networks)，則如同是透過 VPN 業者提供的一道隱密加密的隧道來接取網際網路上的資訊，這個加密隧道也阻止了 ISP 知道用戶連到哪些網站進行何種活動。
![](https://riseup.net/vpn/how-vpn-works/vpn-01_large.png)

![](https://riseup.net/vpn/how-vpn-works/vpn-02_large.png)
photo credit: riseup.net

這份研究主張現今 IPS 對於一般消費者用戶的網路隱私干擾已大幅降低，故其125頁的文件絕大部份的重點，反而是擺在網路産業生態系中其它業者的介紹，如：社交媒體公司、搜尋引擎服務、網頁電郵與聊天訊息軟體、手機作業系統尤其是智慧型手機改變了用戶上網習性、網路廣告商、瀏覽器，線上影音和電子商務、跨站追縱、跨設備多方追縱。Swire　等人認為，在網際網路商業化蓬勃發展的20年後，上述網路產業比之 ISP 能更針對性地監控與收集更多更精準的用戶個人資料，也對其資訊自主與隱私權的威脅傷害更為巨大，故此份文件的花了大半篇幅來細數這幾類業者如何地收集用戶資料，何㮔類型的個資，如何透過這些「個人數據黑金」來創造、鞏固其利潤追求模式。有興趣了解網際網路當前商業模式下主要的用戶個資隱私被收集使用的態系，此份文件或許算是一個不錯的入門讀物。

[註1] 然而在 2017年三月，美國國會終究還是立法通過，同意讓 ISP 業者可以取得更放寬的自由度，除非用戶有明確拒絕，否則即假設其已同意授權 ISP 業者可處分、出售用戶資料給第三方。隨後在當年12月，川普所任命的 FCC 新主席領軍下，再次以多數決推翻了二年前把 ISP 列入公共承運人之決議，主張它們只是一般的資訊服務業者，其管制規範密度也大為減輕。


