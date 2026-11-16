# LLM Research Wiki｜作業繳交說明

## 1. 專案簡介

本專案建立一個繁體中文的 LLM 研究 Wiki。它參考 Karpathy 的 LLM Wiki 構想，把研究資料分成原始來源、整理後的知識頁面與 AI 維護規則三個層次。使用者只需要把論文或文章放入 `raw/`，AI 就能依照 `AGENTS.md` 的規則進行收錄、摘要、交叉連結、索引更新與品質檢查。

目前網站以「可持續累積的研究知識庫」為主題，展示專案目的、檔案結構、工作流程、AI 維護規則及已完成成果。

## 2. GitHub Repository 連結

請將本專案上傳至自己的 GitHub Repository，並將網址填入下方。

`https://github.com/你的帳號/llm-research-wiki`

## 3. 網頁成果連結

啟用 GitHub Pages 後，將網址填入下方。

`https://你的帳號.github.io/llm-research-wiki/`

本地預覽方式是直接開啟 `site/index.html`。

## 4. AGENTS.md

專案規則在根目錄的 `AGENTS.md`。它定義研究範圍、資料夾用途、收錄流程、查詢流程、證據引用、版本處理和 Wiki 健檢方式。

## 5. 如果之後要新增頁面，AI 如何繼續完成？

將新來源放入 `raw/papers/`、`raw/articles/` 或 `raw/reports/`，再對 AI 下達以下指令：

> 請依照 AGENTS.md 收錄這份新資料。先閱讀 wiki/index.md 與相關 Wiki 頁面，再建立來源摘要，更新相關概念與研究問題，補上交叉連結、索引與日誌。所有可驗證主張請標註來源定位，並檢查 Markdown 連結是否有效。

若要從 Wiki 產生研究成果，可以使用：

> 請只使用已收錄在 Wiki 的內容，整理成 notes/<topic>.md。公式使用 LaTeX，資料不足處標為待驗證，最後列出尚未收錄但值得參考的公開文獻。接著產生 slides/<topic>.md 和 site/<topic>/index.html。

## 6. 專案特色

- AI 維護規則具體，後續可以重複使用。
- 原始資料與 AI 整理結果分層保存，方便追溯。
- Wiki 頁面透過索引和相對連結形成知識網絡。
- 可由同一套資料產生研究筆記、逐頁簡報和 HTML 網頁。
- 研究筆記支援 LaTeX，適合記錄模型、演算法與數學公式。
