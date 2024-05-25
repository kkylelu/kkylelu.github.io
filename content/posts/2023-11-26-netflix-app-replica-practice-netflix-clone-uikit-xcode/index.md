---
title: 復刻 Netflix APP 初步練習｜Netflix clone, UIkit, xcode
date: 2023-11-26
excerpt: 
url: 2023/11/26/netflix-app-replica-practice-netflix-clone-uikit-xcode
thumbnailImagePosition: left
thumbnailImage: /images/K-Lix Icon Design.avif
categories:
  - Swift 學習筆記
  - 作品
tags:
  - Xcode
  - Netflix
  - Cloneapp
  - Interface Builder
  - Swift

---
身為資深劇迷，Netflix 可以說是我的第三個家（第一個家是史萊姆，第二個是動畫瘋～巴哈我大哥）。
<!--more-->


{{< toc >}}


上禮拜開始，我決定要給自己一個挑戰 — **試著刻出一個 Netflix App…**其中的 3 頁**！**

畢竟有多少機會能把自己喜歡的片單都排進全球熱門排行呢🔥？

其實一開始只是想藉這個機會，好好熟悉 Xcode 的 Interface Builder，學習用表格建立一個電子書 app，所以先找了設計師前輩做的 UI。但後來想想，既然要做，乾脆就模仿此時此刻的 Netflix UI，雖然這樣更有挑戰性，但這樣日後回顧時會更有趣！

## 學習目標

1. 搭配 tab bar controller & navigation controller

2. 學習 table view controller with static cells 

3. 學習 scroll view 用法

4. 使用 segue 串接頁面

5. 熟悉常用元件的屬性



## Demo

經過這陣子跟 Interface Builder 搏感情，終於刻出 87 分滿意的畫面，真是恍如隔世啊～

![KLix_1125.gif](KLix_1125.gif)

{{< youtube NDTCZwTo0IA >}}


## 開發階段

### 第一步：挑選設計稿

知道這次電子書 app 是為了要學習表格式 app 的做法，思考了一陣子決定選擇 Netflix，於是到 [Figma community](https://www.figma.com/community) 選擇喜歡的素材。

在這裡我花了大概 1 個小時，實在太有趣了～沒想到有這麼多設計師會熱心分享自己復刻的 App UI 素材，包含 IG、Spotify、Threads…等。

![2023-11-17 at 12.54.11.avif](2023-11-17%20at%2012.54.11.avif)

![2023-11-17 at 12.54.42.avif](2023-11-17%20at%2012.54.42.avif)

注意右下角有作者最後更新的日期，有些作者會標榜 1.0 和 2.0，但不同作者的更新時間不一樣，很可能會遇到 A 作者的 2.0 比 B 作者 1.0 還早發佈的情況，想要找最新素材的同學可以留意一下。



### 第二步：設計基礎框架

參考 Netflix 原本的 App 架構，我使用：

- Tab Bar Controller 做為基底

- Table View Controller 當容器

- Navigation Controller 進出不同頁面

搭配這些元素之後，APP 的雛形就出爐囉！



**拆解首頁、分集介紹頁架構**

通常是 Tab Bar Controller 在第一個，後面可以跟許多 Navigation Controller

   ![2023-11-25 at 00.41.19.avif](2023-11-25%20at%2000.41.19.avif)

   ![2023-11-25 at 00.45.22.avif](2023-11-25%20at%2000.45.22.avif)

   Tab Bar Controller 在第一個，後面可以跟許多 Navigation Controller

   



![2023-11-25 at 00.48.07.avif](2023-11-25%20at%2000.48.07.avif)

用 table view controller 當首頁、分集介紹頁的容器，容器架構都是這樣：

1. 上方：以 container view 作為任意門，呼叫 view controller 

2. 下方：以 table view（紅框處）, scroll view（黃框處） 做出片單

   ![2023-11-25 at 00.37.45.avif](2023-11-25%20at%2000.37.45.avif)



### 第三步：美化設計細節

打造了骨骼精奇的架構，再來就是進行醫美手術拉皮的部分，這部分就要出動 Interface Builder，我針對：

- 字型、大小

- 圖片、顏色

- 按鈕、標籤

等等元素調整格式，讓畫面看起來更接近原生 Netflix。

這時候已經 87 分像了！
邊滑 APP 邊思考要塞哪些片單進去，我就這樣霸氣的掌控 Netflix 的 AI（有夢最美），決定哪些片單要讓它紅！



![2023-11-25 at 00.53.29.avif](2023-11-25%20at%2000.53.29.avif)
*利用 Interface Builder 的 Attributes Inspector 調整屬性，包含字體圖片的顏色格式等*

![2023-11-25 at 00.54.34.avif](2023-11-25%20at%2000.54.34.avif)
*利用 Interface Builder 的 Size Inspector 調整尺寸、位置等*



### 第四步：串接不同頁面

最後一道工法就是用 Segue 把各頁面的按鈕和畫面串連起來。



![2023-11-25 at 00.55.34.avif](2023-11-25%20at%2000.55.34.avif)
*這藍線一個沒連好就是剪不斷理還亂*



修修改改好幾次之後...

我的復刻 Netflix — KLix APP 終於大功告成🎉

![K-Lix Icon Design.avif](K-Lix%20Icon%20Design.avif)

還興奮的請 AI 幫我畫個 APP 的 icon 以茲紀念！

## 開發小結

雖然只是初步刻 APP 的 UI 畫面，還沒到真正 coding 的階段，不過在各種畫面和屬性之間打轉，從原本的粗心漏看欄位，到可以強勢置入喜歡的片單，點擊後還可以對應產生頁面，還是很開心、很有成就感！



**第一版和目前畫面對比**

這是我的第一版畫面，其實我原本單純想照著 Figma 的範例做，因為設計師都已經把料備好了，我就不用煩惱內容，專心疊積木就好。

![Simulator Screen Recording - iPhone 15 Pro - 2023-11-20 at 23.46.13.gif](Simulator%20Screen%20Recording%20-%20iPhone%2015%20Pro%20-%202023-11-20%20at%2023.46.13.gif)


只是看到同學們陸續都上傳作業了，讓我開始思考人生想到其實既然要做，跟著目前最新的 UI 做，雖然比較有挑戰性，但更有趣、更有現代感！就決定調整首頁主視覺。



如果再做一次，我會特別留意素材、元件和 view 這幾點（那不就是全部了嗎？）：

**素材相關**

1. 可以先用現成的，等架構都沒問題再來一口氣更新，比較省時間。

2. 圖片先批次處理成同樣的尺寸和解析度，可以省下後續許多瑣碎調整的工夫。

**元件屬性相關**

1. 想調整 Tab bar 和 Navigation bar 的顏色，要找關鍵字叫做「Style」的，而不是 color ，否則會找到一把火牙起來。

2. button 的 image 跟斯斯一樣有兩種，一種是 symbol 會跟文字排列，放入的圖片多大就是多大；一種是取代文字，整張 button 就是一張圖，這種就可以透過 custom 調整大小。

3. 1 個 button 如果塞不下/不能自由調整 symbol 或字型，可以拆成 2 個 button。

**view 相關**

1. table view 的 section header 內建不能變顏色和大小，可以另外新增 Table View Cell 來裝 Label 。

2. scroll view 的做法很特殊，要記得新增超長的 view 在裡面，以及留意 contentSize 的長度。



## Storyboard 佈局大合照

時間的關係，主要集中火力在練習 table view 相關的元件，目前播放影片都是用圖片暫代，期待開始 coding 後，可以換成真正會動的影片！（不過礙於版權還是不能放真正片源啦～）

![2023-11-25 at 14.21.05.avif](2023-11-25%20at%2014.21.05.avif)



## Github 交作業

<https://github.com/kkylelu/netflix_onepage>



## 參考文件

- [Netflix UI Kit (Mobile iOS) – Figma](https://www.figma.com/community/file/1133841519580847725) 

- [⑨⑤ UIButton 的 N 種玩法. (iOS 15 up) 以 storyboard 與 UIKit 設定… | by Min | 彼得潘的 Swift iOS App 開發教室 | Nov, 2023 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/%E2%91%A8%E2%91%A4-uibutton-%E7%9A%84-n-%E7%A8%AE%E7%8E%A9%E6%B3%95-28db3d113bc6)

- [利用 iOS 15 的 UIButton.Configuration 實現圖片維持比例的 button，圓形 button & 點選時變色 | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發問題解答集 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E5%88%A9%E7%94%A8-ios-15-%E7%9A%84-uibutton-configuration-%E5%AF%A6%E7%8F%BE%E5%9C%96%E7%89%87%E7%B6%AD%E6%8C%81%E6%AF%94%E4%BE%8B%E7%9A%84-button-324cfc95001c)

- [讓 view 變圓角的 layer.cornerRadius. 透過設定 view 的… | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發問題解答集 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E8%AE%93-view-%E8%AE%8A%E5%9C%93%E8%A7%92%E7%9A%84-layer-cornerradius-54aa7afda2a1)

- <https://medium.com/彼得潘的-swift-ios-app-開發問題解答集/ios-15-的-static-cells-的-section-header-footer-顯示問題-a19031321955>

- [\#129 從 Figma Community 練習實作 App 畫面 | by 彼得潘的 iOS App Neverland | 彼得潘的 100 道 Swift iOS App 謎題 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84%E8%A9%A6%E7%85%89-%E5%8B%87%E8%80%85%E7%9A%84-100-%E9%81%93-swift-ios-app-%E8%AC%8E%E9%A1%8C/129-%E5%BE%9E-figma-community-%E7%B7%B4%E7%BF%92%E5%AF%A6%E4%BD%9C-app-%E7%95%AB%E9%9D%A2-cb7a1d774c56)

- [設定 content size，實現水平捲動，上下捲動和分頁的 scroll view | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發問題解答集 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E5%9C%A8-storyboard-%E8%A8%AD%E5%AE%9A-content-size-%E5%AF%A6%E7%8F%BE%E6%B0%B4%E5%B9%B3%E6%8D%B2%E5%8B%95%E7%9A%84-scroll-view-2710fa247293)





## 版權聲明

本作品中所使用的所有圖片及素材，皆來自網絡公開分享資源。如果有任何圖片或素材不小心用了你的作品，請聯絡我以便適當處理。本作品**沒有**這些圖片或素材的版權，也**不會**用來盈利。

