# Changelog

## [2.1.0 (44)] - 2026-09-06

- `WO-WOVEN-HTML-V44-20260906`：依使用者本次授權，把最新 App 的相符來源轉為 HTML，更新既有 GitHub main／官方 Pages 首頁。
- 新增 `woven-prompt-mobile-2.1.0-v44.html`（1,044,506 bytes）；SHA-256 `03BD1203B578A394B6DE24842B30A7C05E6C099E3A2E2E7BEB1AB2ED4531F91D`。保留 v28／v25，不覆寫舊成品。
- 更新繁體中文／English、四區生成流程介紹與所有開啟／下載連結；修正新版 App 已不存在的 HTML 購買入口指引。
- 174 份 App 來源逐檔比對通過；App.tsx 保持不變，只增加獨立 Web 入口、License 公鑰對接與資產內嵌。保留永久 License 協定及儲存鍵。
- 驗證：TypeScript、227/227 功能、4/4 版本、20 項實際 Web UI；Chrome／Edge 兩代 License 的缺少／無效／有效／重開／竄改拒絕；離線 file 開啟無外部請求或缺件；首頁下載雜湊一致，320–1440px 顯示正常。
- 瀏覽器實際匯出備份後重新匯入成功；Android 實機／actual APK → HTML 備份／Play 測試購買保留獨立待辦。
- 公開範圍只有 HTML 與本倉庫文件；沒有 source、APK／AAB、私鑰或個人 License；未新增 tag／Release 或改動權限。

## [Unreleased] - 2026-09-05

- `WO-DRIVE-GITHUB-ALIGN-20260905-v2`：Drive 公開成品 checkout 已快轉到 GitHub 的 1.2（28）；補齊 AGENTS、CHANGELOG、handoff 與 manual manifest，維持公開 HTML 成品邊界。
- 建立／對齊 portable manual manifest，區分工作 branch、GitHub default branch 與 Drive 同步。
- 驗證：v28 大小 727,054 bytes；SHA-256 77fc9edaf66e04e76bd6400fcc9123eca1b4940291215b7cb2bafbab71d31dad，與 Mobile html-preview 的既有 v28 成品逐位元一致。GitHub 既有 main 基底 10457c0；本輪不重建 HTML。
- 本輪為 source／文件 checkpoint；不新增 tag／Release。
