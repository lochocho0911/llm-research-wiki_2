# 上傳 GitHub 與發布網頁

在 GitHub 建立一個空的 Repository，例如 `llm-research-wiki`。進入本專案根目錄後執行：

```bash
git init
git add .
git commit -m "建立 LLM Research Wiki 課程專案"
git branch -M main
git remote add origin https://github.com/你的帳號/llm-research-wiki.git
git push -u origin main
```

接著在 GitHub 的 Repository 設定中開啟 GitHub Pages，將來源設定為 `main` 分支的 `/root` 資料夾。網站入口是根目錄的 `index.html`，會自動導向 `site/index.html`。

發布後，把 Repository 網址和 Pages 網址複製到 `SUBMISSION.md`，即可完成老師要求的繳交資訊。
