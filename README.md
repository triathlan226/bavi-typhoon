# 颱風巴威 BAVI (2026) 各國預測路徑動畫

單一 HTML 檔的互動動畫地圖，比較美軍 JTWC、日本氣象廳 JMA、台灣中央氣象署 CWA、中國中央氣象台 CMA 對 2026 年第 9 號颱風「巴威」的預測路徑。手機、電腦都能看。

## 怎麼用

直接用瀏覽器打開 `index.html` 即可。進頁後自動播放，可以：

- ▶ 播放／暫停，拖曳時間軸
- 點「1x」切換 2x / 4x 速度
- 點上方各國名稱開關該國路徑線
- 點路徑上的點看該時間點的風速、氣壓

## 上傳到 GitHub 分享給朋友

1. 到 https://github.com/new 建一個新 repository（例如 `bavi-typhoon`），選 Public
2. 進入 repo 頁面 → **Add file → Upload files** → 把 `index.html` 拖進去 → Commit
3. 到 repo 的 **Settings → Pages** → Source 選 `Deploy from a branch`，Branch 選 `main`、資料夾 `/ (root)` → Save
4. 等 1–2 分鐘，網址就是 `https://你的帳號.github.io/bavi-typhoon/`，傳給朋友即可

## 自動更新

路徑資料在 `data.json`，網頁載入時自動讀取。`.github/workflows/update.yml` 是自動更新機器人：

- **自動**：每 6 小時抓一次 JTWC 最新官方報文，解析後更新 `data.json` 並自動 commit
- **手動按鈕**：到 repo 的 **Actions → auto-update-typhoon-data → Run workflow**，按一下即可立即更新
- 限制：只有 JTWC 能自動更新（唯一有穩定機器可讀的文字報文）；JMA / CWA / CMA / ECMWF 需手動編輯 `data.json`

## 資料來源與注意事項

- JTWC：第 25 報（2026-07-07 03Z），官方數值預報
- JMA：2026-07-07 晨間官方預報（預報圓中心，經日本媒體轉載）
- CWA / CMA：兩機構未以文字公布逐點座標，路徑係依 7/6–7/7 官方說明（「從台灣東北部海面通過」「登陸或擦過台灣北部、再於浙閩交界登陸」）**近似繪製，僅為示意**
- 早期觀測路徑部分點位為內插近似
- ⚠ 本頁非官方產品，僅供參考。防災資訊請以[中央氣象署](https://www.cwa.gov.tw/V8/C/P/Typhoon/TY_NEWS.html)發布為準
