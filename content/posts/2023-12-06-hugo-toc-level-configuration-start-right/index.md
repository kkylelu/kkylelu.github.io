---
title: Hugo TOC 階層設定：讓文章目錄從正確的地方開始
date: 2023-12-06
excerpt: 
url: 2023-12-06-hugo-toc-level-configuration-start-right
thumbnailImagePosition: left
thumbnailImage: /2023-12-06-hugo-toc-level-configuration-start-right/2023-12-08%20at%2011.56.33.avif
categories:
  - Hugo 網站新手上路
tags:
  - Hugo
  - TOC

---  

套用 hugo-tranquilpeak-theme 這個佈景主題的 TOC 之後，發現目錄（TOC）怪怪的，它會空出一個莫名的階層，像是故意留位置給 H1 標題，但我的文章標題通常是從 H2 開始。
<!--more-->

![2023-12-08 at 11.56.33.avif](2023-12-08%20at%2011.56.33.avif)
*文章目錄不知為何空一個階層*

原本覺得有點傻眼，該不會要去改 layout 之類的文件？不過還好有先回頭查了一下佈景主題作者的[說明文件](https://github.com/kakawait/hugo-tranquilpeak-theme/blob/master/docs/user.md#display-table-of-contents)，發現原來 Hugo 預設目錄是從 H2 開始。如果沒有調整設定，直接套用這個 Hugo 主題的話，它會把 H1 也放進目錄裡。

原來是作者大大老早就提醒了，是我自己沒注意到😅

![2023-12-08 at 11.57.58.avif](2023-12-08%20at%2011.57.58.avif)
*作者早就開示預設從 H1 開始*

所以，我就跑去`Config.toml`這個設定檔的 `[markup]`區塊，把`startLevel`改成2。

![2023-12-08 at 12.00.20.avif](2023-12-08%20at%2012.00.20.avif)
*把 startlevel 改成 2，就會從 H2 開始*

這樣目錄就會從 H2 開始顯示，不會再預留一個奇怪的空階層囉！

![2023-12-08 at 12.01.24.avif](2023-12-08%20at%2012.01.24.avif)
*看起來介面清爽又整齊！*