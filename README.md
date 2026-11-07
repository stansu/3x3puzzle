# 拼圖所 · 3×3 滑動拼圖

上傳一張自己的照片，切成九塊，滑動拼回完整畫面。
單一 HTML 檔、免安裝、免後端，適合直接放在 GitHub Pages 分享給朋友。

![手機版預覽](preview-mobile.jpg)

## 功能

- 上傳手機相簿或電腦裡的圖片，自動置中裁切成正方形
- 支援拖放圖片、貼上剪貼簿圖片
- 點擊、滑動或方向鍵操作滑動拼圖
- 步數、計時、最佳紀錄（存在瀏覽器本機）
- 「看原圖」預覽、重新打亂
- 完成後顯示完整照片與紙花動畫
- 手機、平板、桌面的響應式版面
- 照片只在瀏覽器本機用 Canvas 處理，不會上傳到任何伺服器

## 操作方式

| 操作 | 說明 |
| --- | --- |
| 滑動拼圖 | 點擊空格旁邊的拼圖，讓它滑進空格 |
| 手勢 | 在棋盤上往想移動的方向滑動 |
| 鍵盤 | 使用方向鍵滑動拼圖 |
| 看原圖 | 暫時查看完整照片 |
| 重新打亂 | 保留目前照片，重新開始一局 |

計時會在第一次移動時開始；拼回完整畫面後停止，並保存最快時間。

## 本機預覽

直接雙擊 `index.html`，用瀏覽器開啟即可遊玩，不需要安裝或啟動伺服器。

## 部署到 GitHub Pages

### 用網頁介面

1. 在 GitHub 建立一個新的 **Public repository**。
2. 將 `index.html` 上傳到 repo 根目錄（`README.md` 和 `preview-mobile.jpg` 可一起上傳）。
3. 進入 repo 的 **Settings → Pages**。
4. 在 **Build and deployment** 選擇：
   - Source：**Deploy from a branch**
   - Branch：`main`
   - Folder：`/ (root)`
5. 按下 **Save**，等待約 1～2 分鐘。
6. 網址會是：

```text
https://<你的帳號>.github.io/<repo名稱>/
```

例如帳號是 `alice`、repo 名稱是 `photo-puzzle`：

```text
https://alice.github.io/photo-puzzle/
```

把網址傳給朋友，或做成 QR code 讓朋友掃碼即可。

> 如果 repo 名稱取為 `<你的帳號>.github.io`，網站會直接位於 `https://<你的帳號>.github.io/`。

### 用命令列

```bash
git init
git add index.html README.md preview-mobile.jpg
git commit -m "Add 3x3 sliding photo puzzle"
git branch -M main
git remote add origin https://github.com/<你的帳號>/<repo名稱>.git
git push -u origin main
```

推送後再到 **Settings → Pages** 啟用 Pages。

## 更新網站

修改 `index.html` 並推送後，GitHub Pages 通常會在幾十秒到幾分鐘內更新。
如果朋友還看到舊版，請重新整理頁面，或稍等 CDN 快取更新。

## 隱私

- 朋友選擇的照片只在該裝置的瀏覽器內處理，不會上傳到 GitHub 或任何伺服器。
- 請不要把私人照片放進 repo；預設的「暮色山稜」是由程式即時繪製，不含私人圖片。
- 最佳時間使用 `localStorage` 保存，只存在各自的裝置與瀏覽器中。

## 自訂

- 主色、背景色：修改 `index.html` 裡 `:root` 的 CSS 變數（例如 `--accent`）。
- 預設圖片：修改 `makeDefaultArtwork()` 函式，或將它替換成固定圖片網址。
- 若不想公開程式碼，可改用 Cloudflare Pages 或 Netlify 搭配私有 repo；GitHub Pages 免費方案需要公開 repo。

## 檔案結構

```text
.
├── index.html          # 完整拼圖程式（HTML / CSS / JS 全內嵌）
├── README.md           # 本說明
└── preview-mobile.jpg  # README 用的手機版預覽圖
```
