---
title: 認識 UI 元件｜Xcode  
date: 2023-11-17
excerpt: 
url: /2023/11/17/understanding-ui-components-xcode
thumbnailImagePosition: left
thumbnailImage: /images/Xcode.002.avif
categories:
  - Swift 學習筆記
tags:
  - Xcode
  - Ui Component
  - Swift

---
這次來認識一下 Xcode 裡頭的 UI 元件，畢竟初來乍到，總是要跟前輩們拜個碼頭，讓之後的 swift coding 之路更加順利（是時候跟同學們一起團購綠色乖乖了？）。
<!--more-->


{{< toc >}}


## 目標

UI 元件前輩拜訪清單如下：

Segmented Control，Slider，Switch，Activity Indicator View，Progress View，Page Control，Date Picker，Visual Effect View with Blur，Color Well



說到 UI 前輩就不能不來推薦他最振奮人心的這首歌：

{{< youtube jeqdYqsrsA0 >}}

哦這是 IU 晶醬🎤

總之，就用這帶來好心情的旋律展開 UI 研究吧！

![2023-11-16 at 23.26.48.avif](2023-11-16%20at%2023.26.48.avif)


[參考官方文件](https://developer.apple.com/design/human-interface-guidelines/color-wells)



**⭐️英語小教室**

以下是經常會看到的英文單字

- Progress 進度：特別指**已完成**的部分。

- Track 軌道：特別指**未完成**的部分。

- Tint 顏色：輕微的著色，通常會用在 button 或 track 上。



### Segmented Control

切換 2 個（或以上）的分類

1. Segments  控制分類數量

2. Segment  選擇該分類

3. Title  分類的名稱

4. Image  分類的圖示

5. Selected  選擇目前指定的區塊


![Xcode.002.avif](Xcode.002.avif)
![Xcode.003.avif](Xcode.003.avif)


### Slider

滑動設定數值，e.g. 控制音量

1. Value  調整數值

2. Minimum 最小值

3. Maximum 最大值

4. Min Image 最小值的 icon

5. Max Image 最大值的 icon

6. Min Track  靠近最小值的滑桿顏色

7. Max Track  靠近最大值的滑桿顏色

8. Thumb Tint  滑桿頭的顏色

![Xcode.004.avif](Xcode.004.avif)
![Xcode.005.avif](Xcode.005.avif)


### Switch

開關，e.g. 開關鬧鐘

1. State  開關的狀態（On/ Off）

2. On Tint  打開（On）的底色

3. Thumb Tint 開關頭的顏色

![Xcode.006.avif](Xcode.006.avif)
![Xcode.007.avif](Xcode.007.avif)

### Activity Indicator View

活動進度條，e.g. 資料下載中

1. Style  大小

2. Color  顏色

3. Animating  是否轉動？（在模擬器顯示）

![Xcode.008.avif](Xcode.008.avif)
![Xcode.009.avif](Xcode.009.avif)


### Progress View

顯示進度條，e.g. 活動進行多久

1. Style  Default 圓角/ Bar 直角

2. Progress  目前進度，可填 0\~1  

3. Progress Tint  進度條**已完成**的顏色

4. Track Tint  進度條**未完成**的顏色

5. Progress Image  進度條**已完成**的填充圖片

6. Track Image  進度條**未完成**的填充圖片


![Xcode.010.avif](Xcode.010.avif)
![Xcode.011.avif](Xcode.011.avif)


### Visual Effect View with Blur

毛玻璃效果

Blur Style  模糊化效果/遮罩程度

![Xcode.012.avif](Xcode.012.avif)
![Xcode.013.avif](Xcode.013.avif)


### Page Control

顯示目前分頁數和目前在第幾頁

1. \# of Pages  總共有幾個分頁

2. Current  目前所在分頁（從 0 起算）

3. Hides for Single Page  

   如果 # of Pages  只有一頁，就不顯示此 Page Control

4. Tint Color  非當前分頁圓點的顏色

5. Current Page  當前分頁圓點的顏色

![Xcode.014.avif](Xcode.014.avif)
![Xcode.015.avif](Xcode.015.avif)


### Date Picker

選擇時間日期，e.g. 選擇 2023/11/16

1. Preferred Style  偏好樣式（視窗/滾輪/日曆）

2. Mode  時間/日期/日期＋時間/倒數計時

3. Locale  根據特定時區調整時間格式

4. Interval  設定最短時間間隔（1min\~30min）

5. Date  預設顯示日期

6. Minimum Date  最早可選擇的日期

7. Maximum Date  最晚可選擇的日期

![Xcode.016.avif](Xcode.016.avif)
![Xcode.017.avif](Xcode.017.avif)

### Color Well

選擇顏色，e.g. 自訂喜歡的顏色

1. Color  預設顏色

2. Supports Alpha  是否支援不透明度

3. Title  點擊後彈出視窗的標題

![Xcode.018.avif](Xcode.018.avif)
![Xcode.019.avif](Xcode.019.avif)


為了避免之後金魚腦，整理成簡報方便複習：
<iframe src="https://www.slideshare.net/slideshow/embed_code/key/4R5zaDnrPKbTmQ?startSlide=1" width="597" height="486" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px;max-width: 100%;" allowfullscreen></iframe><div style="margin-bottom:5px"><strong><a href="https://www.slideshare.net/nbnb6712/ui-xcodepdf" title="UI 研究中｜Xcode.pdf" target="_blank">UI 研究中｜Xcode.pdf</a></strong></div>


## 參考文件

[研究以下 UI 元件: Segmented Control，Slider，Switch，Activity Indicator View，Progress View，Page Control，Date Picker，Visual Effect View with Blur，Color Well | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發教室 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/%E7%A0%94%E7%A9%B6%E4%BB%A5%E4%B8%8B-ui-%E5%85%83%E4%BB%B6-segmented-control-slider-switch-activity-indicator-view-progress-view-page-control-date-71acc5b2dd7e)



感謝學長用心智圖給我的啟發💡

[作業#3 — 研究各種 UI 元件 - 彼得潘的 Swift iOS App 開發教室 - Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/%E4%BD%9C%E6%A5%AD-3-%E7%A0%94%E7%A9%B6%E5%90%84%E7%A8%AE-ui-%E5%85%83%E4%BB%B6-b95d33395295)