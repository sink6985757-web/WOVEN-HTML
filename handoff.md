# Handoff

## 目前狀態

- 更新：2026-09-05，Codex；工作單 `WO-DRIVE-GITHUB-ALIGN-20260905-v2` 已確認。
- Drive 公開成品 checkout 已快轉到 GitHub 的 1.2（28）；補齊 AGENTS、CHANGELOG、handoff 與 manual manifest，維持公開 HTML 成品邊界。
- 驗證：v28 大小 727,054 bytes；SHA-256 77fc9edaf66e04e76bd6400fcc9123eca1b4940291215b7cb2bafbab71d31dad，與 Mobile html-preview 的既有 v28 成品逐位元一致。GitHub 既有 main 基底 10457c0；本輪不重建 HTML。
- GitHub：`sink6985757-web/WOVEN-HTML`，default branch `main`。本輪成果以本文件所在 commit 識別；完成非 force push 後，以 `git ls-remote origin refs/heads/main` 與 GitHub API 回讀核對。
- Checkpoint：`manual`；三個 authority immutable SHA 已寫入 `.agents/project-lifecycle.json`，不啟用 standing_scoped。

## 風險與保留

公開 repo 只包含已批准 HTML 成品與本倉庫治理文件；不可加入 Mobile 私有 source、APK、License、私鑰或個人備份。APK → HTML 真實備份往返與實機購買流程未於本輪重驗，不能以 hash 一致代替功能驗收。

既有測試與版本歷史查閱 CHANGELOG／Git；沒有本輪執行的裝置、安裝、部署或帳號驗證不得視為重新通過。

## 唯一續跑點

推送後回讀 GitHub Pages build、根入口與 v28 下載雜湊；後續新版先在 Mobile 完整驗證，公開成品另行對版。

跨裝置接續先讀 manifest、AGENTS、本檔與 Git 狀態，fetch 並比較 default branch。GitHub SHA 回讀與 Drive 雲端回讀分別記錄；若任一未完成，保留該項 PARTIAL，不推論整體已同步。
