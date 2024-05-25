---
title: 為什麼我的 GitHub 小綠點（貢獻值 contributions）沒出現？
date: 2023-10-16T10:33:26+00:00
excerpt: 
url: /2023/10/16/why-github-contributions-green-dot-not-showing/
thumbnailImagePosition: left
thumbnailImage: /images/K.Lu-231016.avif
categories:
  - Swift 學習筆記
tags:
  - contributions
  - GitHub
  - 小綠點
  - 貢獻值

---
在 Xcode 裡面辛苦 commit 和 push，結果跑去 GitHub 一看，小綠點根本沒出現！問題可能出在你的 Git Email 和 GitHub Email 不一樣。
<!--more-->

![](/images/K.Lu-231016.avif)

{{< toc >}}

最近遇到一個讓我很頭痛的問題，就是我明明在 Xcode 裡面 commit 和 push 了，結果跑去 GitHub 看，那個讓人心情愉悅的小綠點（貢獻值 contributions）竟然沒出現！這就像是辛苦種了一畝田，結果發現彎腰半天都沒插到秧，讓人傻眼。

![](小綠點-2023-10-16-at-20.10.29.avif)
*沒記錄到小綠點（貢獻值 contributions）*

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 摘要 {.wp-block-heading}

經過一番調查和查閱 GitHub [官方文件][1]，終於發現問題出在哪，原來是我在本機 Git 的 Email 和 GitHub 的 Email 不一樣，所以 GitHub 就對不起來。

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 解決步驟 {.wp-block-heading}

我是怎麼找回寶貴的小綠點呢？以下有 3 個步驟：

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

### 步驟 1：查一下本機的 Git Email {.wp-block-heading}

首先打開終端機，然後輸入這個指令來查查看：

```git
git config --global user.email
```

你會發現，可能就像我一樣，Email 寫錯了。<figure class="wp-block-image size-full">

![](2023-10-14-at-13.18.26.avif)
*終端機顯示我打錯的 email*

我原本寫的是 `hi@kyle.com`，但正確的應該是 `hi@kylelu.com`

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

### 步驟 2：修改本機的 Git Email {.wp-block-heading}

為了讓 GitHub 能正確追蹤到我們的貢獻，可以選擇用 GitHub 提供的匿名 Email。這樣既可以保護隱私，又能確保貢獻值能夠連動。

在 Xcode 裡，去 `Source Control > Git` 的地方，然後填上 GitHub 提供的匿名 Email，像這樣：

![](xcode-畫面-2023-10-14-at-13.07.30.avif)
*在 xcode 中我改用 GitHub 提供的匿名信箱*

**要怎麼找到 GitHub 提供的匿名信箱？**

到 Settings > Primary email address 就可以看到囉！

![](匿名信箱-2023-10-16-at-17.46.23.avif)
*在 Settings > Primary email address 可以看到 Github 提供的匿名信箱*

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

### 步驟 3：發布前確認 Email 是相同的 {.wp-block-heading}

在 push 之前，特別留意一下，看看 commit 資訊裡面的 Email 是不是對的。這樣才能確保你的貢獻值會被正確記錄啦。

![](push-email-2023-10-14-at-13.12.58.avif)
*發布前可以看看 commit 資訊裡面的 Email 是不是跟 GitHub 的 Email 一樣*

push 後順利在個人頁面上出現小綠點囉！

![](小綠點-2023-10-14-at-13.14.52.avif)
*push 後順利出現小綠點* 

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

幸好我在練習的時候就發現這個問題，也找到了解決的方法。下次如果你在 GitHub 的個人頁面上沒看到小綠點，起手式可以先檢查一下你的 Email 設定，說不定問題就出在這裡！

<div style="height:30px" aria-hidden="true" class="wp-block-spacer">
</div>

## 參考資料 {.wp-block-heading}

[Why are my contributions not showing up on my profile?][1]

 [1]: https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-profile/managing-contribution-settings-on-your-profile/why-are-my-contributions-not-showing-up-on-my-profile