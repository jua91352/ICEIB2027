## Why

**Goal（目標）**：把 DIC3 期末專題 **FMPA（Fresh Market Price Forecast Agent）** 從「課堂簡報 + README」升級成一篇可投稿 **ICEIB 2027（IEEE track）** 的會議論文初稿，並且讓整個改寫過程可追蹤（OpenSpec 規格 → Overleaf LaTeX → 修改前/後版本）。

目前 Overleaf 上只有一份通用的 IEEEtran 模板（`ICEIB2027-IEEE.zip`），每一節都是 placeholder；DIC3 的研究故事（現價錨定、7/14 天日曆天、LLM 不自行算價、誠實揭露未勝基線）散落在簡報與 README，尚未依 **A2Z SOP**（A–Z 查核點）組織成論文。DIC4 要求「Agent + Overleaf MCP 撰寫 LaTeX」與「用 OpenSpec 管理 Abstract / Intro / Related Work 的投稿內容」，因此現在需要一份明確的規格，讓 Agent 依規格改寫、讓老師與組員能逐條驗收。

## What Changes

- **Abstract（A–F）**：以 Attention Getter → But → Cure → Development → Experiments → Findings 六句式重寫摘要，並補上 IEEE keywords。
- **I. Introduction（G–L）**：加入公開證據引題、問題定義、既有方法分類與評論、三個研究問題（RQ1–RQ3）與三項貢獻（C1–C3）、文章結構說明。
- **II. Related Work（M–O）**：約 1/2 AI 技術（價格預測 ML、樹模型、LLM Agent/工具使用、MCP）+ 1/2 領域知識（零售價格黏性、價格傳遞不對稱、颱風衝擊、公開資料）；新增 8 欄 **Article Summary Table**，最後歸納 Existing Research → Limitations → Research Gap → Our Project。
- **III. Proposed Scheme（PA–PM）**：新增系統架構圖（模組 ①–⑤ 編號）、處理流程圖（含資料檢查 / 錯誤回覆分支）、帶行號的 Algorithm 1、A/B 模式公式與符號表。
- **IV. Evaluation（Q–V）**：寫清楚資料（臺中市 13 個公有市場）、樣本數、時間切分與防洩漏規則、基線（不變價、動量）、指標（direction macro-F1、relative-change MAE）；結果表保留作者待填欄位，**不填入未經核對的數字**。
- **V. Conclusion（W–Z）**：回顧動機與挑戰、適用情境、產出（含負向結果）、限制與未來工作。
- **References**：以可查證的真實文獻取代模板中的範例 `shannon1948`。
- **版本管理**：原始模板保存為「修改前」（`paper/before/`），改寫後 LaTeX 快照為「修改後」（`paper/after/`），並附 Overleaf 上傳用 zip。

## Capabilities

### New Capabilities

- `paper-abstract`：A–F 六段式摘要與關鍵字。
- `paper-introduction`：G–L 緒論，含研究問題與貢獻條列。
- `paper-related-work`：M–O 相關研究，AI/領域各半、8 欄文獻摘要表、Research Gap 歸納。
- `paper-proposed-scheme`：PA–PM 方法章節，含編號架構圖、流程圖、行號偽碼、A/B 公式。
- `paper-evaluation`：Q–V 實驗設計與結果呈現規則（基線、指標、防洩漏、不得虛構）。
- `paper-conclusion`：W–Z 結論、限制與未來工作。
- `paper-integrity`：引用真實性、數據誠信、AI 使用揭露、修改前/後版本與 Overleaf 編譯規範。

### Modified Capabilities

- （無；本 repo 先前沒有任何 spec。）

## Impact

- `latex/main.tex`：標題、作者、加入 TikZ 套件。
- `latex/sections/00_abstract.tex`、`01_introduction.tex`、`02_related_work.tex`、`03_proposed_scheme.tex`、`04_experiments.tex`、`05_conclusion.tex`：全部改寫。
- `latex/tables/comparison.tex`（改為 FMPA 基線比較表）、新增 `latex/tables/article_summary.tex`、`latex/tables/notation.tex`。
- 新增 `latex/figures/architecture.tex`、`latex/figures/flowchart.tex`（TikZ，Overleaf 可直接編譯）。
- `latex/references.bib`：換成真實文獻。
- `paper/before/`、`paper/after/`：修改前/後快照與 zip。
- 不影響 DIC3 程式碼；數值結果仍須作者從 DIC3 實驗紀錄核對後填入。
