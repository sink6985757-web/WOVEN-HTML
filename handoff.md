# Handoff

## 目前版本

- 日期：2026-09-06；工作單 `WO-WOVEN-HTML-V44-20260906`，依本次使用者明確更新 GitHub／首頁的授權執行。
- 版本：**Woven Prompt HTML 2.1.0（44）**。固定入口：[官方首頁](https://sink6985757-web.github.io/WOVEN-HTML/)。
- 成品：`woven-prompt-mobile-2.1.0-v44.html`；1,044,506 bytes；SHA-256 `03BD1203B578A394B6DE24842B30A7C05E6C099E3A2E2E7BEB1AB2ED4531F91D`。
- App source fingerprint：`DB375D379577A60A929B8B748FD8063D4ED498EDD651B4DA2B56A1983DE4DF52`（174 files）。保留相符 Android App；Web 專用入口沿用 legacy／Cloud 公鑰與 License 協定，將圖示內嵌至單檔。
- 原 v28／v25 的內容保持不變。公開倉庫只存 HTML 成品與本倉庫文件，不包含私人來源、原生安裝檔或個人 License。
- GitHub 成果：`main` @ `b8c9a3a17200098d7ada35471e15bfd2859dcb26`；Pages 同一 commit `built`。正式首頁與 committed bytes 相符；HTML 下載與本機成品逐位元一致。收工文件以包含本紀錄的提交為準，沿用已授權 scoped checkpoint 回讀。

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
- 新版 Android App 沒有離線 HTML 購買入口；首頁改為沿用既有 License，不宣稱可在新版 App 新購買。
- 瀏覽器語音及外部 AI 網站可能需網路；HTML 不執行原生廣告或購買。
- 本機 Drive 路徑已更新；未另做 Google Drive 雲端同步回讀。

## 唯一續跑點

新版本接續先 fetch，比較目前 upstream 與 default main，再回讀 Pages commit 與目前下載雜湊。需要進行實際 APK 備份或購買驗收時，使用獨立工作範圍。若 Web 版本發現問題，將首頁開啟／下載連結改回 `woven-prompt-mobile-1.2-v28.html` 並新增 rollback commit，不刪檔、不 force push。

## 最近收工

- 時間：2026-09-06T21:01:34+08:00；Agent：Codex。
- 本輪 HTML／官方首頁更新：**VERIFIED / 已完成**。版本化成品與首頁已實際回讀；收工只有 CHANGELOG／handoff 兩檔差異。
- Policy：`manual`，沿用本次明確發布範圍；無新 tag／Release、權限或商店操作。
- 下一步：使用者需要接續時，先核對目前 main 與 Pages，再處理獨立的實機 APK 備份驗收。不要因歷史待驗而重建或重傳已發布 HTML。
