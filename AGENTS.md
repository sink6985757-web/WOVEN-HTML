# WOVEN-HTML

目前公開成品為 2.1.0（44）；既有 v28／v25 完整保留。以獨立 Mobile 專案的相符來源產生經驗證的 HTML，維持公開成品與私有來源邊界。

## Portable lifecycle 維護契約

- 專案：`sink6985757-web/WOVEN-HTML`；default branch：`main`；Git root 必須是本 repository。
- 依 `.agents/project-lifecycle.json` 使用 manual checkpoint；authority pin 指向已回讀的治理來源。
- Startup 只讀文件與 Git，fetch 後同時確認 upstream／default branch；不得用工作 branch 已同步冒充 default branch 已包含成果。
- Shutdown 每次更新 CHANGELOG／handoff；README 隨人類安裝、使用或版本變化更新。
- 本次已確認工作單的授權沿用至其範圍完成；不得擴張到 tag／Release、權限、刪除或封存。
- 公開 repo 只包含已批准 HTML 成品與本倉庫治理文件；不可加入 Mobile 私有 source、APK、License、私鑰或個人備份。APK → HTML 真實備份往返與實機購買流程未於本輪重驗，不能以 hash 一致代替功能驗收。
