# YouTube Deep Link Redirector

讓 IG 用戶點擊連結後直接開啟 YouTube App，而不是被困在 in-app browser。

## 部署到 Vercel

1. 把這個資料夾 push 到 GitHub
2. 到 [vercel.com](https://vercel.com) 連結你的 repo
3. 點擊 Deploy，完成！

或者用 Vercel CLI：
```bash
npm i -g vercel
vercel
```

## 使用方式

部署完成後，你會得到一個網址，例如 `https://your-project.vercel.app`

### 連結格式

```
https://your-project.vercel.app/?v=VIDEO_ID
```

或者用更短的路徑：
```
https://your-project.vercel.app/yt?v=VIDEO_ID
https://your-project.vercel.app/watch?v=VIDEO_ID
```

### 範例

如果原本的 YouTube 連結是：
```
https://www.youtube.com/watch?v=dQw4w9WgXcQ
```

改成：
```
https://your-project.vercel.app/?v=dQw4w9WgXcQ
```

貼到 IG bio 或限動連結，用戶點擊就會直接開 YouTube App！

## 運作原理

1. 用戶點擊連結 → 進入這個 landing page
2. 頁面自動偵測是 iOS 還是 Android
3. 使用對應的 URL scheme 嘗試開啟 YouTube App
   - iOS: `vnd.youtube://` scheme
   - Android: Intent URL
4. 如果 App 沒裝或開不了，用戶可以點按鈕在網頁版觀看

## 自訂 Domain（推薦）

在 Vercel 設定一個短網域會更專業，例如：
- `yt.yourname.com`
- `watch.yourname.com`

這樣連結就會變成 `yt.yourname.com/?v=VIDEO_ID`，看起來更乾淨！
