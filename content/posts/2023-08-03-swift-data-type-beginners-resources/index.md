---
title: Swift 學習筆記：基本型別、初學者資源
date: 2023-08-03T15:31:54+00:00
thumbnailImagePosition: left
thumbnailImage: /images/K.Lu-230803.avif
url: /2023/08/03/swift-data-type-beginners-resources/
categories:
  - Swift 學習筆記
tags:
  - ios
  - swift
  - 學習資源

---

開始決定學習程式語言 Swift 後，我先問 ChatGPT 如何學好這門程式語言，它的建議是：
<!--more-->

![](/images/K.Lu-230803.avif)

{{< toc >}}

  1. **學習 Swift 語言**  
    Swift 是 Apple 的程式語言，用於開發 iOS、macOS、watchOS 和 tvOS 應用程式。你可以從 Apple 的 **[Swift Playgrounds][1]** 或者線上教學平台如 **[Codecademy][2]**、**[Udemy][3]** 等學習 Swift。
  2. **熟悉 Xcode**  
    Xcode 是 Apple 的開發工具，你將在這裡撰寫程式碼、設計使用者介面、測試應用程式等。你可以在 Apple 的 **[Xcode 資源頁面][4]** 找到相關的教學資源。
  3. **學習基本的 iOS 開發概念**  
    這包括了瞭解 MVC（Model-View-Controller）架構、學習如何使用 UIKit 或 SwiftUI 來設計使用者介面、瞭解如何使用 Core Data 來儲存資料等。
  4. **實作專案**  
    透過實作專案來學習是非常有效的方式。你可以從簡單的專案開始，例如製作一個計算機或者天氣應用程式，然後逐漸嘗試更複雜的專案。
  5. **閱讀官方文件和參考資源**  
    Apple 提供了非常完整的 **[開發者文件][5]**，這是一個很好的學習資源。
  6. **參加社區和學習小組**  
    參加一些 iOS 開發者的社區，例如 **[Stack Overflow][6]**、**[iOS Dev Weekly][7]**、**<Swift.org> [Forums][8]** 等，可以讓你有機會學習到最新的開發技術和趨勢，並且可以在遇到問題時尋求幫助。
  7. **持續學習和實踐**  
    iOS 開發是一個持續學習和實踐的過程。Apple 每年都會更新他們的作業系統和開發工具，因此你需要持續學習來跟上最新的開發技術和趨勢。

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## Swift 四大學習點 {.wp-block-heading}

根據上述，我開始找相關學習資源，意外發現[彼得潘][9]提到 Swift 有四大學習點：

  1. 變數：var
  2. 運算：加減乘除、整數、負數
  3. 條件：if else
  4. 迴圈：for, while

這提供我明確的學習方向，在找相關學習資源時，就會特別留意這方面的解說。<figure class="wp-block-image size-full">

![](四大學習者-2023-08-03-at-23.41.18.avif)
*Swift 四大學習點：變數、運算、條件、迴圈*

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 初學者資源 {.wp-block-heading}

我從以下 3 項學習資源，了解 Swift 的上述知識點基本觀念

### 遊戲化學習 {.wp-block-heading}

[Swift Playgrounds][1]  
想要最直覺看到程式碼「動起來」，就玩 Apple 官方出品的 Swift Playgrounds ，結合闖關和解謎要素，可以根據關卡目標，了解指令、函數、條件…等應用，真的卡關也可以看提示說明，反思自己可以改進的地方。


![](playground-2023-07-30-at-16.16.02.avif)
*Swift Playgrounds 可以從遊戲中很直覺學習程式碼的作用*

### 生活化舉例 {.wp-block-heading}

[Swift 5 Programming Bootcamp For Beginners][10]  
用射擊遊戲、APP 登入畫面、做 Pizza 等生活化的舉例，因此雖然是英文語音，但老師語速很慢，搭配字幕反覆看很好理解。

![](swift-5-for-beginngers-2023-08-03-at-23.00.31.avif)
*Swift 5 Programming Bootcamp For Beginners以射擊遊戲說明程式碼*

### 參考書籍 {.wp-block-heading}

[iOS 16 App 程式設計實戰心法][11]  
參考網友評價、比較目前市面最新 swift 教學書和翻看試閱本後，我買了這本電子書作為上述網路資源的輔助，除了因為作者教學讓我比較能理解以外，更棒的是它提供了 swiftUI 和 UIkit 兩種版本教學，還加贈一年更新，也就是未來 iOS 17 推出後，也可以獲得更新後的電子書內容。我想先從 UIkit 學起，這樣之後想學 swiftUI 也可以參考本書。

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 目前學到的知識點 {.wp-block-heading}

目前已經學習完 Swift Playgrounds 的體驗課程和 Swift 5 Programming Bootcamp For Beginners，整理學習到的知識點如下：<figure class="wp-block-table">

| 型別      | 名詞    | 用途                                                                                            |
| ------- | ----- | --------------------------------------------------------------------------------------------- |
| var     | 變數    | &#8211; int 整數：例如 0,1,2,100  
&#8211; Double 浮點數：例如 1.34, 2.9  
&#8211; String 字串：可以放名字、訊息、文章 |
| let     | 常數    | 指定後就不能更改                                                                                      |
| for     | 迴圈    | 執行一定次數後停止                                                                                     |
| while   | 迴圈    | 直到滿足條件才停止                                                                                     |
| If else | 條件    | 滿足特定條件採取動作                                                                                    |
| func    | 功能    | function 的縮寫，它是一件任務或工作的描述，可以打包一系列動作。                                                          |
| //      | 註解    | 在程式碼中不會被執行的說明文字                                                                               |
| !       | 邏輯運算子 | NOT 反轉值，如果程式碼為 != 就是「不等於」的意思。                                                                 |<figcaption class="wp-element-caption">swift 基本型別</figcaption></figure> 

除此之外為了要保持程式碼的可讀性，需要注意「camelCase」（駝峰式大小寫）

命名長串字母，要像駱駝的駝峰一樣，有大寫小寫字母，但第一個字一定是小寫，例如：

| 正確          | 錯誤          |
| ----------- | ----------- |
| loginButton | loginbutton |
| firstName   | Firstname   |
*表格舉例* 

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 問題點紀錄 {.wp-block-heading}

在學到 func 可以結合 return 使用時，腦袋一時轉不過來。

既然可以用 func 執行 task，為什麼需要 return？

舉例：

```swift
func caluclateSomeStuff() -> Int {
 
let value1 = 30
let value2 = 60
 
let result = value1 + value2
return result
}
let resultFromTheFunction = caluclateSomeStuff()

print(resultFromTheFunction)
``` 


原來是在我們需要得知「執行後的結果」，或是進一步處理時，可以使用，以生活化的例子舉例就會是這樣：

| Data type | 餐廳情境   | 辦公室情境      |
| --------- | ------ | ---------- |
| func      | 內場做完餐點 | 交辦助理做事     |
| return    | 提供給客人  | 完成之後提供書面報告 |</figure> 

接下來想試著做一些簡單的練習，試著整合目前學到的知識點。

 [1]: https://www.apple.com/tw/swift/playgrounds/
 [2]: https://www.codecademy.com/learn/learn-swift
 [3]: https://www.udemy.com/topic/swift/
 [4]: https://developer.apple.com/xcode/resources/
 [5]: https://developer.apple.com/documentation/
 [6]: https://stackoverflow.com/questions/tagged/ios
 [7]: https://iosdevweekly.com/
 [8]: https://forums.swift.org/
 [9]: https://medium.com/@apppeterpan?source=---two_column_layout_sidebar----------------------------------
 [10]: https://www.udemy.com/course/swift-5-programming-bootcamp-for-beginners/
 [11]: https://www.appcoda.com.tw/swift/