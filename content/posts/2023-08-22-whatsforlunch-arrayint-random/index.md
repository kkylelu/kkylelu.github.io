---
title: 今天午餐吃什麼？Array、Int random 練習
date: 2023-08-22T08:34:51+00:00
url: /2023/08/22/whatsforlunch-arrayint-random/
thumbnailImagePosition: left
thumbnailImage: /images/K.Lu-230822.avif
categories:
  - Swift 學習筆記
  - 作品
tags:
  - ios
  - swift

---
辦公室總是有午餐選擇困難症？點點按鈕找靈感吧！
<!--more-->

![](/images/K.Lu-230822.avif)

{{< toc >}}

## 作品目的 {.wp-block-heading}

為了解決每日的午餐選擇困難症，透過這個小專案，可以隨機挑選午餐，並熟悉 Swift 的基礎知識。
![](2023-08-13-at-12.46.59-1.gif)

## 學習目標 {.wp-block-heading}

  1. 熟悉 Xcode 介面
  2. 掌握 Array 陣列的使用
  3. 學會使用 Int random 隨機函數

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## APP 的主要功能 {.wp-block-heading}

按下按鈕時，APP 會隨機推薦以下五種料理，並附上示意圖。這些圖片我都是使用 [Canva][1] 製作，並且利用 [App Icon Generator][2] 產出 3 種大小，提供 Xcode 使用。

  1. 中式：炒飯 
  2. 韓式：石鍋拌飯 
  3. 美式：漢堡 
  4. 日式：壽司 
  5. 越式：河粉 

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 製作步驟 {.wp-block-heading}

### 1 設計介面 {.wp-block-heading}

  * 使用 Interface Builder 來設計 APP 介面。
  * 更改背景顏色：選擇 View -> Attributes Inspector -> Background。
  * 在 imageView 中，我們要放入 Label、image 和 button。確保每個元件都有正確的 Auto Layout constraints。

### 2 連結介面 {.wp-block-heading}

  * 使用 IBOutlet 和 IBAction 來連接 UI 元件和程式碼。
  * 將圖檔和按鈕都連結到 ViewController：按著鍵盤的 Control 並拖曳圖檔和按鈕 (Control-drag) 到 ViewController 的 code，在 Interface Builder 和 code 之間建立連接。

### 3 定義常數 {.wp-block-heading}

  * 使用 let 關鍵字來定義不可變的常數。
  * 使用 `#imageLiteral(resourceName: "料理圖片名稱")` 來直接在 code 中插入圖片，這蠻酷的，第一次知道 swift code 可以出現縮圖！不過圖片如果都是文字很容易看不清楚。

```swift
let foodImages: [UIImage] = [
#imageLiteral(resourceName: "us"),
#imageLiteral(resourceName: "vn"),
#imageLiteral(resourceName: "jp"),
#imageLiteral(resourceName: "cn"),
#imageLiteral(resourceName: "kr")
]
```


### 4 連結按鈕和圖片 {.wp-block-heading}

  * 使用 @IBAction 來響應按鈕的點擊事件。
  * 利用 Int.random(in:) 來隨機選擇一個食物的圖片。

```swift
@IBAction func chooseFood(_ sender: UIButton) {
let randomIndex = Int.random(in: 0..<foodImages.count)
foodImageView.image = foodImages[randomIndex]
}
```



### 5 設定自動佈局 {.wp-block-heading}

自動佈局(Auto layout) 可以確保 APP 在各種裝置和螢幕尺寸上都保持原樣、不會跑版。我覺得它很像 PPT 的「群組」功能，不僅可以對齊物件(alignment)，還能調整大小 (distribution)！  
不過要排得整齊，我還在學習，目前了解到要注意這 3 點：

  1. 從小區塊開始建立 view，再到 stacked view，最後建立整體的 stacked view。
  2. 抓出每個區塊的 fill equally。
  3. 為了避免壓到手機邊界，要設定 safe area
  
  
![](2023-08-21-at-22.32.02-768x608.gif)

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

自動佈局要排得好，還有很多值得深入研究的地方，請教 ChatGPT 後，它提供以下建議：

  1. 理解 Constraint 的優先級： 
      * 每個 Constraint 都有一個優先級，範圍從 1 到 1000。預設為 1000，代表這是一個必要的約束。
      * 較低的優先級意味著約束可以在需要時被打破。
  2. 使用 Stack View： 
      * Stack View 是一個非常強大的工具，可以自動管理其子視圖的佈局。
      * 它可以是水平或垂直的，並且可以設定間距、對齊和分佈。
  3. 避免使用絕對座標： 
      * 當設計介面時，盡量避免使用固定的座標值。這樣可以確保你的介面在不同尺寸的螢幕上都能正確地呈現。
  4. 使用 Safe Area： 
      * Safe Area 是 iOS 11 引入的一個新概念，它考慮到了如瀏海、Home 指示器等特殊的 UI 元素。確保你的內容都在 Safe Area 內，可以避免被這些元素遮擋。
  5. 預覽多種裝置和方向： 
      * 使用 Xcode 的 Interface Builder 中的 Preview 功能，可以同時預覽多種裝置和方向的介面。這樣可以確保你的佈局在所有情況下都正確。
  6. 使用 Size Classes 進行適應性佈局： 
      * Size Classes 允許你根據裝置的尺寸和方向定制你的介面。例如，你可以為 iPad 和 iPhone 設計不同的佈局。
  7. Debugging Auto Layout： 
      * 如果你的佈局出現問題，Xcode 會在 Interface Builder 中用紅色和橙色線條來指示。
      * 學會解讀這些提示，並使用 Xcode 的 Debug View Hierarchy 功能，可以幫助你更快地找到和解決問題。



## 參考資源 {.wp-block-heading}

  * [iOS & Swift &#8211; The Complete iOS App Development Bootcamp][3]： Cht5-Ch6
  * [How To Make An App For Beginners (iOS/Swift &#8211; 2019) ：Ch13][4]
  * [App Icon Generator][2]
  * [Canva][1]

 [1]: https://canva.com/
 [2]: https://www.appicon.co/#image-sets
 [3]: https://www.udemy.com/course/ios-13-app-development-bootcamp/
 [4]: https://www.udemy.com/course/how-to-make-an-app-for-beginners-iosswift-2019/