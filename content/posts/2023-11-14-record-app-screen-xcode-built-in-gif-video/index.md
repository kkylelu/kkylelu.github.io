---
title: 錄製 App 操作畫面 - xcode 內建錄製 Gif 影片 
date: 2023-11-14
excerpt: 
url: /2023/11/14/record-app-screen-xcode-built-in-gif-video
thumbnailImagePosition: left
thumbnailImage: /images/K.Lu-231114.avif
categories:
  - Swift 學習筆記
tags:
  - Xcode
  - Gif
  - 螢幕錄影

---
每天有那麼多 app 誕生，我們很少有閒情逸致可以下載 app 後把玩幾天再決定要不要用。
<!--more-->


{{< toc >}}


除非你有開盲盒的興趣，或是把 app 當轉蛋在開箱。

更多時候我們會在下載 app 前做一件事 — 看 app 預覽畫面。



## 用圖片或影片預覽 app 

基本款是看圖片，會有 app 的操作介面、主打功能等等

![KL_2023-11-14 at 11.25.11.avif](KL_2023-11-14%20at%2011.25.11.avif)
*app store 的 app 預覽圖片畫面*



用心一點的 app 像 [Kono 電子雜誌](https://apps.apple.com/us/app/kono-magazine/id477224666) 還會提供影片，在短短 30 秒內精銳盡出，省得下載後才發現我們不適合。（這裡有官方提供的 [App 預覽規格](https://developer.apple.com/tw/help/app-store-connect/reference/app-preview-specifications)）

![2023-11-14 at 11.38.58.gif](2023-11-14%20at%2011.38.58.gif)
*app 提供影片預覽*



雖然說下載只是不到 30 秒鐘的事情

但如果花個 3 秒鐘，就能少浪費 3 倍以上的時間

拿來追更多劇不是更好嗎？

什麼？可以邊下載 app 邊追劇？

那我們今天這堂課就上到這邊。



## Gif 比影片更體貼

同樣的，在看一篇 app 介紹文章時，如果懶得跳出去找 app store 的介紹，這時候更體貼讀者的做法就是「提供 GIF 預覽圖」

這樣讀者不會因為跑去 app store 一去不復返忘了回來，也不用伸長已經快抽筋的大拇指點擊影片播放鍵，就能好好欣賞 app 大作

還沒使用到 app ，好感度先加 50 分！



## 幫還沒上架的 iOS app 錄製 Gif

原本我都是用截圖軟體 [CleanShot](https://cleanshot.com/) 幫還沒上架的 iOS app 錄影

不過新學到一招更直覺的方法—直接用 xcode 內建錄影功能！



![play_2023-11-14 at 12.05.58.avif](play_2023-11-14%20at%2012.05.58.avif)
*點擊左上角播放鍵，啟動模擬器*



![record_2023-11-14 at 12.02.40.avif](record_2023-11-14%20at%2012.02.40.avif)
*可以選擇 *File* > *Record Screen**



推薦直接用快速鍵：Command + R 鍵來開始錄製比較快

錄完後，右下角會出現一個小跟班

![savegif_2023-11-14 at 12.04.29.avif](savegif_2023-11-14%20at%2012.04.29.avif)
*在小預覽畫面按右鍵選擇 Save as Animated GIF*



記得在這個小預覽畫面按右鍵，選擇 Save as Animated GIF 

這樣就會自動存在桌面囉！



![Simulator Screen Recording - iPhone 15 Pro - 2023-11-14 at 12.09.13.gif](Simulator%20Screen%20Recording%20-%20iPhone%2015%20Pro%20-%202023-11-14%20at%2012.09.13.gif)
*xcode 內建 app 錄影功能*


比起 CleanShot 錄製畫面， xcode 內建錄影**沒有**手機的 mockup ，可能少了一點 fu ，但錄製起來方便很多！尤其是搭配快速鍵，發現自己動作不流暢就二話不說重來，非常直覺。

要選擇另外用截圖軟體，或用 xcode 內建功能錄製 Gif，就看個人取捨囉。



## 參考文件

[熟悉 App gif 錄製，GitHub，Medium - 彼得潘的 Swift iOS App 開發教室 - Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/%E7%86%9F%E6%82%89-app-%E5%BD%B1%E7%89%87%E9%8C%84%E8%A3%BD-github-medium-%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84ios-app-%E4%BD%9C%E6%A5%AD-646d009f43fc)