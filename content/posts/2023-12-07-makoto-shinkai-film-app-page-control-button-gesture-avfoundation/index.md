---
title: 新海誠電影 app｜page control, button, gesture, AVFoundation
date: 2023-12-07
excerpt: 
url: 2023-12-07-makoto-shinkai-film-app-page-control-button-gesture-avfoundation
autoThumbnailImage: false
thumbnailImagePosition: "top"
thumbnailImage: /2023-12-07-makoto-shinkai-film-app-page-control-button-gesture-avfoundation/shinkaiMovie_cover3.avif
metaAlignment: center
categories:
  - Swift 學習筆記
  - 作品
tags:
  - page control
  - gesture
  - AVFoundation
  - shinkai

---
> 知道生命很短暫，我知道死亡隨時會來臨，即使如此，再一年、再一天，就算只是再一小時，我們都想活下去！\
> ——《鈴芽之旅》
<!--more-->


{{< toc >}}


![shinkaiMovie_cover2.avif](shinkaiMovie_cover2.avif)



每一幀畫面都可以當桌布，這是我對新海誠動畫作品的印象。



從《秒速五公分》開始入坑新海誠宇宙，到後來的《言葉之庭》，災難三部曲《你的名字》、《天氣之子》到今年上映的《鈴芽之旅》，一開始會被精緻畫面吸引，再來會跟著故事劇情展開冒險，最後反覆回味新海誠想傳達的價值觀，作品既有娛樂性又富有寓意。

對他的稱呼也慢慢從新海誠、新海導演，變成誠哥，是這個世代我最喜歡的動畫導演。為了表達支持、瞭解他的創作理念和一窺幕後秘辛，很少買電影周邊的我，還入手了電影海報相框組、官方美術設定集和捨不得拆封的藍光光碟。

趁這次練習，就來簡單介紹他的災難三部曲吧！



## 學習目標

1. 運用 page control, button & gesture 手勢滑動。

2. 用 AVFoundation 框架來播放音樂。



## Demo

![Shinkai.gif](Shinkai.gif)
*操作示範 GIF*

{{< youtube qIU8fYGzWWo >}}
*操作示範搭配音樂（注意影片音量）*

## 開發過程

### UI 與素材準備

從 Library 拖曳 UI 元件到 view 上，包含 UILabel、UIPageControl 和 UIButton：

1. `UILabel`：用來顯示文字，像是顯示每個頁面的標題或說明。

2. `UIPageControl`：3 個小圓點，顯示目前在哪一頁。

3. `UIButton`：控制音樂的播放、停止或上下一首。

![2023-12-04 at 17.21.44.avif](2023-12-04%20at%2017.21.44.avif)

把這些元件拖曳到 View 上各就各位，就可以開始來設定功能了。



### 控制上下一部電影：% 餘數

使用 % 餘數來實現循環播放的效果。當我們選到最後一部電影時，% 餘數讓我們可以回到第一部，創造一種無限循環的感覺，就像新海誠的電影總是讓人回味無窮一樣。

- 下一部電影：用 % 是為了整除為 0，回到第一部

- 上一部電影：假設 index 是 0 （第一部），用「總數 -1 」就會回到最後一部

請 GPT 整理成表格說明：

| **操作** | **代碼** | **邏輯說明** | **示例（假設 movie.count = 3）** | 
|---|---|---|---|
| 下一部電影 | **`(index + 1) % movie.count`** | 將索引增加 1，然後用電影總數取餘數以循環回到開始位置 | 如果索引為 2，下一個索引為 (2 + 1) % 3 = 0 | 
| 上一部電影 | **`(index + movie.count - 1) % movie.count`** | 將電影總數加到索引上，減去 1，然後取餘數以處理負索引情況 | 如果索引為 0，下一個索引為 (0 + 3 - 1) % 3 = 2 | 

寫成 swift 會長這樣：

```swift
// 下一部電影
    
    @IBAction func next(_ sender: Any) {
        /*
         `% movie.count` 以 % 取餘數，讓計算結果等於 0，就會回到第一部重來，達到無限循環的效果。
         例如 movie.count 共 3 部電影，index 到第 2 部時 (2 + 1) % 3 = 0，回到第一部。
        */
        index = (index + 1) % movie.count
        updateUI()
        
    }
   
    
    
    // 上一部電影
    /*
     將電影總數加到 index 上，減去 1，然後取餘數避免變成負數
     如果 index 為 0，下一個 index 為 (0 + 3 - 1) % 3 = 2，回到最後一部
     */
    @IBAction func pre(_ sender: Any) {
        index = (index + movie.count - 1) % movie.count
        updateUI()
    }

```


有趣的是有這些常見生活案例都會用到：

1. **圖片輪播器**：例如臉書或 IG 常見的輪播圖片或廣告，電商或新聞網站也有。

2. **新聞或文章滾動**：在新聞網站或 APP 中，會有看不完的文章。

3. **日曆或時間選擇器**：時鐘或日期的循環顯示。

4. **音樂播放器播放列表**：循環播放音樂。

5. **遊戲開發中的物件循環**：例如跑酷遊戲的背景和障礙物。

6. **社群媒體的動態消息**：每次刷新臉書或 IG 的動態消息，也是會自動循環播放。

### AVFoundation 載入背景音樂

這裡運用 AVFoundation 框架播放音樂，新海誠的配樂絕對是畫龍點睛，這裡就放我喜歡的三首《前前前世》（夢燈籠也很讚！）、《GrandEscape》和《KANATA HARUKA》，前奏太長還有特地剪過才放上來。

流程如下：

1. **導入 AVFoundation**：首先要導入框架，才能使用它的功能。

2. **創建 AVPlayer**：接著命名一個 AVPlayer，用來控制音樂播放。

3. **更新 UI 並加載音樂**：在 **`updateUI`** 函數中，我們加載音樂並更新播放器的狀態。

4. **控制播放與暫停**：定義相關的動作（action）來控制音樂的播放和暫停。

5. **切換音樂曲目功能**：透過函數來切換上一首和下一首。



這裡有一點要注意，匯入音樂時要放在專案資料夾，而不是 assets 裡面，這樣 code 才讀得到。

![2023-12-05 at 15.54.13.avif](2023-12-05%20at%2015.54.13.avif)

![2023-12-05 at 15.53.34.avif](2023-12-05%20at%2015.53.34.avif)

寫成 swift 會長這樣：

```swift
import UIKit
import AVFoundation

class ViewController: UIViewController {
    
    let audioPlayer = AVPlayer()

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        updateUI()
    }
  
    // UI Updates
    func updateUI(){
        let url = Bundle.main.url(forResource: musicTracks[currentTrackIndex], withExtension: "mp3")!
                let playerItem = AVPlayerItem(url: url)
                audioPlayer.replaceCurrentItem(with: playerItem)
                audioPlayer.play()
        
    }
}
```



在 Swift 中使用 AVFoundation 來加載和播放音樂，就像邀請 RADWIMPS 搖滾樂團來幫新海誠配樂一樣，從畫面和音樂都讓人更沈浸在故事之中，鐵定要用新台幣下架支持！



**相關文章**

[利用 AVPlayer 播放音樂音效. 1 查詢音樂的網址。 | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發問題解答集 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E5%88%A9%E7%94%A8-viewdidload-%E9%BB%9E%E4%B8%80%E9%A6%96%E6%AD%8C-%E6%92%AD%E6%94%BE%E4%B8%80%E6%AC%A1pl-bfe59e9e22c)

<https://github.com/shuhan0628/MovieGesture/blob/main/MovieGesture/MovieViewController.swift>



### Swipe 手勢滑動

既然有輪播圖片，就會想用手指左右滑動，就像看到新海誠電影周邊後，會想左看右看有沒有必買收藏的紀念品一樣直覺。

這裡主要有 4 個步驟：

1. **新增 Swipe 手勢**：確認拖曳  Swipe Gesture Recognizer 元件到 image view 之後，有建立連線。

2. **設定元件數量和方向**：一個 Swipe Gesture 元件只能對應一個方向，所以左右要各拉一個。

3. **允許圖片互動**：打開 image view 的「User Interaction Enabled」選項，讓用圖片可以互動。

4. **連線到切換畫面按鈕**：為了讓左右滑可以切換到上下一部電影畫面，要連線到對應的 @IBAction Function

![2023-12-06 at 16.49.19.avif](2023-12-06%20at%2016.49.19.avif)
*確認 swipe 和 image view 建立連線*



![2023-12-06 at 17.49.49.avif](2023-12-06%20at%2017.49.49.avif)
*打開 image view 的「User Interaction Enabled」選項*



![2023-12-06 at 17.56.09.avif](2023-12-06%20at%2017.56.09.avif)
*拖曳切換音樂 function 的圓點到 swipe 建立連線*



![2023-12-06 at 17.57.49.avif](2023-12-06%20at%2017.57.49.avif)
*確認 swipe 和切換音樂 function 建立連線*



在建立手勢的連線時，發現可以再把先前的 func 架構整併在一起，這樣才方便作業，程式碼也會更簡潔，於是把 movie 和 music 的上下頁切換，從 4 組 function 整併成 2 組。

這邊要特別注意要「按X」取消先前 `preMusic` 的連線，只保留從 `preMovie`  更名後的 `previousPage`，否則 APP 跑兩步就會心肌梗塞閃退。

![2023-12-06 at 22.06.55.avif](2023-12-06%20at%2022.06.55.avif)
*要「按X」取消不需要的連線，才不會造成 app 閃退*



**相關文章**

[開發 iOS App 的 Gesture (手勢)功能 — UIKit 版本 | by 彼得潘的 iOS App Neverland | 彼得潘的 Swift iOS App 開發問題解答集 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E5%95%8F%E9%A1%8C%E8%A7%A3%E7%AD%94%E9%9B%86/%E9%96%8B%E7%99%BC-ios-app-%E7%9A%84-gesture-%E6%89%8B%E5%8B%A2%E5%8A%9F%E8%83%BD-uikit-%E7%89%88%E6%9C%AC-f6cb95075705) 

[\#1 運用 button 、 gesture 、page control更換內容＆背景音樂播放｜黑暗騎士三部曲 | by Yeh | 彼得潘的 Swift iOS App 開發教室 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/1-%E9%81%8B%E7%94%A8-button-gesture-page-control%E6%9B%B4%E6%8F%9B%E5%85%A7%E5%AE%B9-%E8%83%8C%E6%99%AF%E9%9F%B3%E6%A8%82%E6%92%AD%E6%94%BE-%E9%BB%91%E6%9A%97%E9%A8%8E%E5%A3%AB%E4%B8%89%E9%83%A8%E6%9B%B2-ae4b245b4d91)



## 同場加映

---

### 調整 SF symbol 大小

系統預設的 large 實在不 large，直接改 Title 大小也沒有動靜，琢磨了很久，終於發現有 Configuration 可以調整！

1. 打開 Attributes inspector，找找看 `Default Symbol Configuration` 區塊

2. 在 `Configuration` 欄位有 `Point Size`  輸入想要大小數值就可以囉。

![SFsymbol_Configuration.gif](SFsymbol_Configuration.gif)



### 調整 Label 內文字縮排

調整 Label 內文字縮排

發現電影介紹的文字沒有縮排，看起來擠成一團

![2023-12-05 at 13.10.22.avif](2023-12-05%20at%2013.10.22.avif)



把 Label 從 Plain 改成 Attributed，我們可以設定更多屬性，如字型、大小、顏色、縮排等。

![2023-12-05 at 13.12.17.avif](2023-12-05%20at%2013.12.17.avif)



可以看到 indent 縮排的部分，原本 Head, First Line 和 Tail 都是 0，全部改成 10 

![2023-12-05 at 13.16.50.avif](2023-12-05%20at%2013.16.50.avif)



這樣文字就有縮排囉！

![Simulator Screenshot - iPhone 15 Pro - 2023-12-06 at 23.53.24.avif](Simulator%20Screenshot%20-%20iPhone%2015%20Pro%20-%202023-12-06%20at%2023.53.24.avif)


## Github

[kkylelu/ShinkaiMovie: 介紹新海誠災難三部曲：你的名字、天氣之子以及鈴芽之旅。](https://github.com/kkylelu/ShinkaiMovie)



## 參考資料

[\#38 利用 page control，segmented control，button & gesture 更換內容 | by 彼得潘的 iOS App Neverland | 彼得潘的 100 道 Swift iOS App 謎題 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84%E8%A9%A6%E7%85%89-%E5%8B%87%E8%80%85%E7%9A%84-100-%E9%81%93-swift-ios-app-%E8%AC%8E%E9%A1%8C/%E7%9C%9F%E6%84%9B%E7%9A%84%E6%A8%A1%E6%A8%A3-image-view-%E5%92%8C-segmented-control-%E7%B7%B4%E7%BF%92-675d64d5c94c)

[\#10 用 page control, button & gesture 更換內容 | by Fraser Chang | 彼得潘的 Swift iOS App 開發教室 | Medium](https://medium.com/%E5%BD%BC%E5%BE%97%E6%BD%98%E7%9A%84-swift-ios-app-%E9%96%8B%E7%99%BC%E6%95%99%E5%AE%A4/10-%E7%94%A8-page-control-button-gesture-%E6%9B%B4%E6%8F%9B%E5%85%A7%E5%AE%B9-f774e22063b5)