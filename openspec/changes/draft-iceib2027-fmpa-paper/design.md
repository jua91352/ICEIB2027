## Context

- **起點（修改前）**：Overleaf 上的 `ICEIB2027-IEEE` 模板——IEEEtran conference class、模組化 `sections/*.tex`，內容全是 placeholder，只有一筆範例引用 `shannon1948`。
- **素材**：DIC3 專題 FMPA 的 README（`AIoT-DIC3-ProjectRefactor/README.md`）、老師的 A2Z SOP（`myRef/A2Z outline example.pdf` → `myRef/A2Z-SOP-reference.md`）、FMPA 簡報解析與資訊圖表（`myRef/`）、期末專題提案作業規範。
- **限制**：
  - ICEIB 2027 IEEE track，4–8 頁，英文，pdfLaTeX。
  - 實驗數字只能來自 DIC3 實驗紀錄；目前手上的資訊圖表（AI 生成）與文字敘述互相矛盾（見 Risks），不能直接當結果。
  - 本機沒有 TeX 環境，編譯以 Overleaf 為準。
- **利害關係人**：作者（學生）、DIC4 授課老師（看 Overleaf 修改前/後 + GitHub 上的 OpenSpec）、未來的會議審稿人。

## Goals / Non-Goals

**Goals:**
- 依 A2Z SOP 把六個章節寫成一篇故事連貫、可投稿的初稿（Abstract A–F → Conclusion W–Z）。
- 滿足課程規範：Related Work AI/領域各半 + 8 欄 Article Summary Table；架構圖模組 ①–⑤ 編號；流程圖；行號偽碼。
- 每一個 `\cite` 都對應到可查證的真實文獻；每一個數字都可追溯。
- 保留「修改前 / 修改後」兩個版本，讓老師可以直接比較。
- 讓 Agent（Claude Code / Antigravity + Overleaf MCP）可以依 `tasks.md` 一節一節地改寫與驗收。

**Non-Goals:**
- 不重新跑 DIC3 實驗、不修改 DIC3 程式碼。
- 不在論文中宣稱模型勝過簡單基線（目前結果並非如此）。
- 不處理投稿系統操作、版權表單與 camera-ready 排版。
- 不把課程 Proposal 的 Deep Research（Q1–Q3 全文）塞進論文；只把 5 個核心思維轉成方法章節的「設計原則」。

## Decisions

1. **論文定位：「Agent 設計 + 誠實評估協定」，而不是「新模型 SOTA」。**
   DIC3 的結果是模型未勝動量／不變價基線。若把貢獻寫成預測準確度，會與結果矛盾；改寫成 (C1) 現價錨定的 Domain AI Agent 架構、(C2) 固定 7/14 日曆天 + 防洩漏 + 強基線的評估協定、(C3) 負向結果與其領域解釋（價格黏性）。
   *替代方案*：只報 RF/HGB 的分數、淡化基線 → 違反研究誠信，也違反作業規範「不得虛構」。

2. **標題**：*FMPA: A Store-Price-Anchored Domain AI Agent for 7- and 14-Day Fresh Vegetable Price Forecasting*。同時點出「現價錨定」「Domain AI Agent」「7/14 天」三個關鍵字。

3. **A2Z 對應方式**：每個 `.tex` 檔內用 LaTeX 註解標示 `% A`、`% G`、`% PA` 等查核點，PDF 上看不到、但老師與 Agent 可以在原始碼逐點核對。
   *替代方案*：在正文寫出 A/B/C 標題 → 不符合 IEEE 論文慣例。

4. **圖用 TikZ 畫在 `figures/*.tex`，不用 PNG。**
   向量、可在 Overleaf 直接改字、Git diff 可讀、不需要另外的繪圖檔。架構圖與流程圖各一個檔案，方便日後換成 draw.io 匯出的 PDF（只要改 `\input` 為 `\includegraphics`）。
   pdfLaTeX 不支援 Unicode 圓圈數字 ①，所以定義巨集 `\cnum{1}` 用 TikZ 畫圓圈編號，圖與正文共用同一個巨集。

5. **8 欄 Article Summary Table 用 `table*` + `tabularx` + `\scriptsize`**，在雙欄版面中橫跨整頁，欄寬固定、文字自動換行。

6. **結果表先放 TODO 巨集**：`\todo{}` 以紅色顯示，提醒作者從 DIC3 實驗紀錄填入；同時在正文中寫出已確認的「定性」結論（未勝基線）。資訊圖表上的數字不使用（理由見 Risks）。

7. **模組化檔案 + Overleaf 工作流**：
   `openspec/changes/.../tasks.md` → Agent 修改 `latex/` → 上傳 Overleaf（或經 Overleaf MCP / Git 同步）→ Overleaf 編譯 → 下載 PDF 放回 `paper/after/`。每節獨立檔案，Agent 一次只改一個檔，衝突最小。

8. **版本保存**：
   - 修改前：`ICEIB paper/ICEIB2027-IEEE.zip`（原始模板）與解開後的 `paper/before/`。
   - 修改後：`latex/` 為工作版本；`paper/after/` 為本次 change 完成時的快照與 zip。
   - `paper/README.md` 用表格列出每一節的修改前／後差異。

9. **語言**：論文英文；OpenSpec 的 proposal / design / tasks 用繁體中文（方便課堂溝通），specs 用英文 SHALL/WHEN/THEN（OpenSpec 驗證格式）。

## Risks / Trade-offs

- [資訊圖表數字與文字矛盾：圖表中 7 天 RF 的 MAE（0.060）低於不變價（0.062），但文字寫「MAE 未勝持平不變價基線」] → 論文不採用圖表數字；結果表用 `\todo`，由作者從 DIC3 原始實驗紀錄核對後填入。
- [本機無法編譯 LaTeX，TikZ 或表格可能有編譯錯誤] → 只用 TeX Live 標準套件；送出前在 Overleaf 編譯，`tasks.md` 保留「Overleaf 編譯通過」為未勾選任務。
- [頁數超過 8 頁] → 8 欄表格用 `\scriptsize`；若超頁，先刪 Related Work 敘述文字、保留表格。
- [文獻幻覺] → 所有文獻經網路查證（DOI / 官方網址），`references.bib` 只收已查證條目；作者投稿前再抽查。
- [「2025 年青蔥單把 380 元」等案例無法查證] → 只在找到正式來源時引用，否則改用官方統計。
- [Overleaf MCP 需要帳號憑證] → 憑證只存在作者本機的 MCP 設定，不進 Git（`.gitignore` 排除 `.claude/settings.local.json`）。
- [Trade-off：誠實報告負向結果可能降低接受率] → 以「評估協定 + 領域解釋」作為貢獻，這也是課程規範要求的研究誠信。

## Migration Plan

1. 修改前版本已凍結（`ICEIB paper/`、`paper/before/`）。
2. 依 `tasks.md` 逐節完成 `latex/`。
3. 在 Overleaf 建新專案上傳 `paper/after/FMPA-ICEIB2027-after.zip`，編譯並下載 PDF。
4. 作者填入實驗數字與作者資訊後，再更新 `paper/after/` 快照。
5. 回復：任何時候都可以重新上傳 `paper/before/` 的 zip 回到模板狀態。

## Open Questions

- 作者名單、所屬單位、通訊 email？
- DIC3 實驗紀錄中的正式數字（macro-F1、MAE，7/14 天、A/B 模式）？
- 是否要在論文中放 Web 原型截圖（Fig. 3）？會增加約 1/3 頁。
- ICEIB 2027 是否要求雙盲（需匿名化作者與 GitHub 連結）？
