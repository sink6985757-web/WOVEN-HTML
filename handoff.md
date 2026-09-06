# Handoff

## 目前版本

- 日期：2026-09-06；工作單 `WO-WOVEN-HTML-V44-20260906`，依本次使用者明確更新 GitHub／首頁的授權執行。
- 版本：**Woven Prompt HTML 2.1.0（44）**。固定入口：[官方首頁](https://sink6985757-web.github.io/WOVEN-HTML/)。
- 成品：`woven-prompt-mobile-2.1.0-v44.html`；1,044,506 bytes；SHA-256 `03BD1203B578A394B6DE24842B30A7C05E6C099E3A2E2E7BEB1AB2ED4531F91D`。
- App source fingerprint：`DB375D379577A60A929B8B748FD8063D4ED498EDD651B4DA2B56A1983DE4DF52`（174 files）。保留相符 Android App；Web 專用入口沿用 legacy／Cloud 公鑰與 License 協定，將圖示內嵌至單檔。
- 原 v28／v25 的內容保持不變。公開倉庫只存 HTML 成品與本倉庫文件，不包含私人來源、原生安裝檔或個人 License。
- GitHub default branch：`main`；既有 Pages source：`main` 的 `/`。版本與文件以本提交為準；完成發布時另核對遠端 SHA、Pages build commit、根入口與下載 SHA，不能只以本機 commit 推定部署。

## ReadyGate：HTML 與首頁

證據截止：2026-09-06T17:10:04.992448+08:00；**READY**，限本版 Web 成品與既有首頁更新。依既有授權 scoped commit／non-force push；無額外 release override。

| 閘門 | 狀態 | 證據 |
| --- | --- | --- |
| G1 目的與範圍 | VERIFIED | 最新 App → 既有 WOVEN-HTML／官方首頁 |
| G2 來源與版本 | VERIFIED | 174 份來源、相符 APK／AAB／ZIP SHA 回讀；App.tsx 未改 |
| G3 相容與公開邊界 | VERIFIED | 固定兩套公鑰、永久 License 與儲存鍵；私有內容掃描、舊檔逐位元保留 |
| G4 成品驗證 | VERIFIED | TypeScript、227/227 + 4/4；20 項 Web UI、Chrome／Edge License 與 offline file；首頁真實下載 hash |
| G5 交付與回復 | VERIFIED | 既有 main/root Pages；保留舊版，出問題可新 commit 將入口切回 v28 |

License 測試使用本機 owner 檔案，報告只記通過結果，不公開內容、識別碼或簽章。沒有替任何買家核發新 License。

## 已知限制

- 實際 APK 匯出 `.woven.json` → HTML、Android 實機升級、Play 測試購買仍為使用者保留的獨立驗收；本輪 Web 備份匯出／重新匯入不替代這些證據。
- 新版 Android App 沒有離線 HTML 購買入口；首頁改為沿用既有 License，不宣称可在新版 App 新購買。
- 瀏覽器語音及外部 AI 網站可能需網路；HTML 不執行原生廣告或購買。
- 本機 Drive 路徑已更新；未另做 Google Drive 雲端同步回讀。

## 唯一續跑點

新版本接續先 fetch，比較目前 upstream 與 default main，再回讀 Pages commit 與目前下載雜湊。需要進行實際 APK 備份或購買驗收時，使用獨立工作範圍。若 Web 版本發現問題，將首頁開啟／下載連結改回 `woven-prompt-mobile-1.2-v28.html` 並新增 rollback commit，不刪檔、不 force push。
