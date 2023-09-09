++
date = "2023-09-18 14:04:00+00:00"
draft = false
title = "ubuntu server on orange pi pc"
slug = "ubuntu-server"
categories = ["others"]
tags = [
  "SBC",
  "ubuntu"
  ]
disable_profile = false
disable_widgets = false
+++

去年買入山寨版的[香橙派單板機小電腦](https://blog.jxtsai.info/post/orangepi/)，老實說其使用頻率很低，主因還是硬體過於低端效能不佳，尤其裝了圖像化桌面環境，電腦跑起來更是吃力，故久而就一如樹莓派2 的宿命，早早被打入冷宫晾在一邊。

上個月開始再重新第 n+1 次學習 python 程式，發現有一款強化版的互動式直譯器 bpython 常好用，簡直可以取代 python documentation 來查找一些模組，函數的使用方法。因為 bpython 不易安裝在 windows ，於是想試試能否在 orangepi pc 安裝使用。

原本在 orangepi PC 使用的是第三方開發作業程式帶 XCEF 桌面環境的 Armbian，進入 GUI 再開啟 terminal，使用體驗上還勉強可接受，但既然只會用到 terminal，那不如乾脆捨棄桌面環境，改安裝純文字指令 CLI 作業系統。Armbian  23.8 Bookworm 雖有帶 python 3.10，但 pip, venv 還得自行安裝。試了直接安裝 bpython 失敗，也無法安裝 ipython。若在 venv 開發擬環境則可以成功安裝 ipython 並使用，但仍無法安裝 bpython 。當然 ipython 也可為作為bpython 的替代品，它可以直接下一些 linux 常用指令還蠻方便的啦。

不過因為想使用 bpython 是我重新拾回 orange pi pc 理由，被執念佔領心神就會讓放下正事去搞些有的沒的週邊。同樣也試著在樹莓派的 PiOS Lite 純文字指令作業系統試著安裝 bpython 亦告失敗。原本都快死心了，才注意到，orangepi pc 除了第三方開發的 armbian 外，還有自家製作的 ubuntu, debian 版本作業系統。樹莓派官方也有 32位元的 ubuntu server 作業系統給老舊機款使用。（ubuntu desktop 則只限 raspberry 3/4 才可安裝）。趕緊下載 ubuntu 20.4 focal server for orangepi pc 並燒錄到 micro SD card。第一次進入系統時，預設的 username/ password 皆為： orangepi, 可利用以下指令來更改密碼。若要變更用戶名稱，則須以 root 帳戶登入，再參考此篇的指令進行修改。 

$ sudo passwd username

若要更改系統預設的用戶名 orangepi 則改由 root 帳號登入並[參考本篇指令](https://learnubuntu.com/change-username/)來修改。如果想改成自己常用的 username 建議先做好這步，再去進行更新或軟體下載，否則次序顛倒容易發生軟體找不到原有路徑的麻煩。

接下來 update/ upgrade 來更新軟體套件。不過  orangepi  官方設定的鏡像下載站點為中國清華大學無法順利連接，因此需更改 /etc/apt/sources.list 的 apt 鏡像下載資訊為 http://ports.ubuntu.com/ubuntu-ports  才順利完成更新與升級。在 ubuntu server 20.4 for orangepi pc 的 python 版本為 3.8.10 可順利直接安裝 bpython/ ipython。而樹莓派 pi 2 的官方 ubuntu server 32 bit 版則已支援到 ubuntu 23.4 版，安裝與設定也更比香橙派直覺方便，可以在使用 rasp imager 燒錄 sd 記憶卡時直接設定用戶名稱和登入密碼，否則則為系統預設的 ubuntu/ ubuntu 。

![img](https://i.imgur.com/5VM1N5r.jpg)

純文字指令環境無法使用滑鼠，也沒有 Ctrl+C V 複製貼上的功能，可以說是非常單純乾淨的學習環境。玩了兩三天又不甘寂莫地想找出更多玩法，ubuntu 自帶 git 無需另行下載，不過比較頭疼的是如何把 [ssh public key](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) 加到自己的 github 帳戶底下，以便更輕鬆地在不同電腦之間進行代碼筆記更新。後來找到的方式是把 micro-sd 取出來在 linux 桌機或筆電上來取讀 ssh key 內容後貼到 github 。 