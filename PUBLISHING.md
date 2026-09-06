# Woven Prompt HTML：GitHub 上架與維護指南

本指南只處理 `WOVEN HTML` 公開成品倉庫。Mobile 原始碼倉庫保持獨立，不得整包複製、加入 Git 或推送到這個公開倉庫。

## 可直接貼到 GitHub 的文案

Repository description：

> Woven Prompt 官方 HTML 入口：有連結即可從瀏覽器開啟，搭配 APK 流程核發的個人 License 使用，也可下載單檔離線保存。

建議 Topics：

```text
woven-prompt  prompt-tool  offline-html  local-first  github-pages
```

目前 HTML 版本（本次未新增 GitHub Release）：

```text
Woven Prompt HTML 2.1.0 (44)
```

目前版本摘要：

> Woven Prompt 2.1.0（44）官方單檔 HTML。可由 GitHub Pages 線上開啟，也可下載成單一 HTML 離線保存。本發佈只包含 HTML 成品與公開維護文件，不包含 Mobile 原始碼、APK／AAB、簽章私鑰或個人 License。下載後可用 SHA-256 `03BD1203B578A394B6DE24842B30A7C05E6C099E3A2E2E7BEB1AB2ED4531F91D` 驗證檔案。

## 1. 公開範圍

可公開的內容：

- 版本化的 `woven-prompt-mobile-*.html` 成品
- GitHub Pages 入口 `index.html`
- 本倉庫的 `README.md`、`PUBLISHING.md`、`AGENTS.md`、`CHANGELOG.md`、`handoff.md`
- `.agents/project-lifecycle.json`（只含公開 repository identity、authority SHA 與相對路徑）
- `LICENSE`、`NOTICE`
- `.gitattributes`、`.gitignore`、`.nojekyll`

不可公開的內容：

- Mobile 的 `app/`、`docs/`、scripts、測試、建置資料夾或完整 Git 歷史
- APK、AAB、keystore、憑證、私鑰、`.env` 或帳號資料
- owner License、買家 License、訂單、Email、個人備份或真實 Prompt
- 未通過驗證的測試產物

## 2. 既有倉庫開工

GitHub repository 已存在：`sink6985757-web/WOVEN-HTML`，default branch 為 `main`。只在本 repository root 操作，不重新 init 或改 remote。

```powershell
git rev-parse --show-toplevel
git remote get-url origin
git fetch origin main
git status --short --branch
git log --oneline --left-right HEAD...origin/main
```

只有乾淨且單純落後時，才在已確認同步工作內執行 `git merge --ff-only origin/main`。治理文件由本 repo 維護，不從 Mobile 複製 AGENTS 或 handoff。

## 3. 既有 GitHub Pages

Pages 已啟用，來源是 `main` 的 `/(root)`，正式入口為 [Woven Prompt HTML](https://sink6985757-web.github.io/WOVEN-HTML/)。推送 main 可能觸發 Pages build；每次同步後回讀 build 狀態、根入口連結與目前 HTML 下載的 SHA-256。GitHub commit 與 Pages 部署完成是兩項驗收。

2026-09-06 更新範圍：加入 2.1.0（44）HTML、更新首頁與公開文件，沿用既有 main/root Pages；保留 v28／v25，不變更 Pages 設定、權限或建立 Release。

## 4. 發布新版本

1. 在獨立 Mobile 專案完成來源修改、測試與 standalone HTML 建置。
2. 驗證版本號、WOVEN Backup schema、官方離線 License adapter、兩套公鑰 Authority 與公鑰指紋符合當版規格。
3. 確認 HTML 不含私鑰、owner License、個人 License、Email、API Key 或其他 secret。
4. 只把新的版本化 HTML 複製到本倉庫，使用下一個已驗證版本的唯一檔名。
5. 更新 `index.html` 中所有線上開啟、離線下載按鈕及目前版本文字。
6. 更新 `README.md` 的版本、檔名、大小與 SHA-256。
7. 在瀏覽器驗收新版後，再使用明確檔案清單進行 commit 與 push。
8. GitHub Pages 完成部署後，回讀正式網址並測試根網址、版本檔網址與下載檔案雜湊。

不要覆寫同名舊檔。若內容改變，應使用新版本檔名，讓 Git 記錄、快取與使用者下載都能清楚辨識。

## 5. 每版最低驗證

### 成品與敏感資訊

```powershell
$html = '.\woven-prompt-mobile-2.1.0-v44.html'
Get-Item -LiteralPath $html | Select-Object Name, Length, LastWriteTime
Get-FileHash -Algorithm SHA256 -LiteralPath $html
rg -n -i 'BEGIN .*PRIVATE KEY|sk-[A-Za-z0-9_-]{20,}|AIza[0-9A-Za-z_-]{30,}|gh[pousr]_[A-Za-z0-9]{20,}|Bearer\s+[A-Za-z0-9._~+/-]{20,}' -- $html
```

最後一個命令預期沒有結果。若找到任何疑似憑證，停止發布並回到來源專案調查，不能只從成品字串中刪除後硬上架。

### 瀏覽器驗收

- 根網址能顯示公開入口，且線上開啟與離線下載按鈕都指向目前版本。
- Chrome 與 Edge 能載入首頁、生成器、智囊團、路由、詞庫與設定頁。
- License 缺少、有效與無效狀態符合預期；測試時不得使用或提交買家個人 License。
- WOVEN Backup v3 能匯出並於同版重新匯入，也能讀取 v2／v1；正式跨 APK／HTML 相容性仍以實際 APK 匯出檔驗收。
- Prompt 生成、保存、搜尋、最愛、初始化與顯示模式可正常使用。
- 點選外部 AI 目的地前會保留 Prompt，且只有使用者主動操作才開啟外部網站。
- 語音不可用時能正常回退鍵盤輸入。

### Git 範圍

```powershell
git status --short
git diff --check
git ls-files
```

`git ls-files` 應只出現本指南第 1 節允許的公開檔案。

## 6. 回退

若新版 Pages 發生問題：

1. 保留問題版本以供調查，不要重寫 Git 歷史。
2. 把 `index.html` 的線上開啟、離線下載按鈕與版本文字改回最後一個已驗證版本。
3. 更新 `README.md` 的目前版本資訊。
4. 提交一個清楚的 rollback commit，推送後重新回讀 Pages。

回退只切換公開入口，不應刪除使用者資料，也不需要 force push。

## 7. 建議的 GitHub Release

每個確認穩定的 HTML 版本可另外建立 GitHub Release，附上：

- 版本號與日期
- HTML 成品
- SHA-256
- 主要變更
- 已知限制
- 是否通過實際 APK → HTML 的 WOVEN Backup v2／v1 相容性驗收

Release 是版本下載與追溯入口；GitHub Pages 則維持指向目前推薦版本。

## GitHub 官方參考

- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
