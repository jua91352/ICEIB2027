# Overleaf 論文：修改前 / 修改後（DIC4 繳交項目 1）

| 版本 | 位置 | 說明 |
|---|---|---|
| 修改前（before） | `before/latex/`、`before/FMPA-ICEIB2027-before.zip` | 原始 ICEIB 2027 IEEE 模板（與 `../ICEIB paper/ICEIB2027-IEEE.zip` 相同），全部為 placeholder |
| 修改後（after） | `after/latex/`、`after/FMPA-ICEIB2027-after.zip` | 依 OpenSpec change `draft-iceib2027-fmpa-paper` 改寫的 FMPA 論文初稿（快照；持續編輯的版本在 `../latex/`） |

## 在 Overleaf 上產生修改前 / 修改後（同一個專案）

1. Overleaf → **New Project → Upload Project**，上傳 `before/FMPA-ICEIB2027-before.zip`（主檔 `main.tex`，編譯器 pdfLaTeX）。編譯後下載 PDF 存成 `before/before.pdf`，截圖存成 `before/overleaf-before.png`。
2. 依講義 Step 2 執行 `setup_overleaf_mcp.ps1`，把這個 Overleaf 專案 clone 到本機並註冊成 MCP。
3. Agent 把 `../latex/` 的內容寫進 clone、commit、push 回 Overleaf。重新編譯後下載 PDF 存成 `after/after.pdf`，截圖存成 `after/overleaf-after.png`。
4. Overleaf 右上角 **History** 會同時保留修改前與修改後兩個版本，可直接給老師看差異。

> **目前 Overleaf 上的修改後版本是專案「FMPA-ICEIB2027-after-v2」**（填入 DIC3 真實數字與作者後重新上傳；舊的「FMPA-ICEIB2027-after」已過時）。
>
> **Overleaf 免費方案（本專案實際情況）**：沒有 Git 存取權，第 2–3 步改為：修改前＝Overleaf 專案「DIC4」（老師模板）；修改後＝把 `after/FMPA-ICEIB2027-after.zip` 用 New project → Existing project (.zip) 上傳成新專案。Agent 的修改前→修改後紀錄在本機 MCP 資料夾 `%USERPROFILE%\overleaf-projects\fmpa-paper` 的兩個 git commit。

## 逐節修改對照

| 章節 / 檔案 | 修改前 | 修改後 | A2Z 查核點 |
|---|---|---|---|
| `main.tex` | 標題 "Your Research Paper Title"、範例作者 | FMPA 正式標題；加入 TikZ、tabularx；`\cnum`、`\todo`、`\tbd` 巨集；AI 使用揭露 Acknowledgment | — |
| `00_abstract.tex` | 3 句 placeholder | 232 字 A–F 六段式摘要 + 6 個 keywords | A–F |
| `01_introduction.tex` | 4 個空 subsection | 公開證據引題、三大挑戰、文獻分類與評論、RQ1–RQ3、C1–C3、文章結構 | G–L |
| `02_related_work.tex` | 1 個範例引用 | AI 技術與領域知識各一節、Research Gap → Our Project | M–O |
| `tables/article_summary.tex` | （無） | 8 欄 Article Summary Table（`table*`） | O |
| `03_proposed_scheme.tex` | 範例公式與 3 行演算法 | 設計目標、M1–M5 設計原則、模組 ①–⑤、公式 (1)–(3)、範例、流程、Algorithm 1（14 行） | PA–PL |
| `figures/architecture.tex` | 空白方框 | TikZ 架構圖（①–⑤，虛線框標出「LLM 不算價」邊界） | PG |
| `figures/flowchart.tex` | （無） | TikZ 流程圖（含資料檢查失敗 → 澄清／錯誤分支） | PI |
| `tables/notation.tex` | （無） | 符號表 | PF |
| `04_experiments.tex` | 4 個空 subsection | 資料與防洩漏、基線、指標公式、參數、結果、討論、效度威脅 | Q–V |
| `tables/comparison.tex` | Baseline A/B、Proposed | 7/14 天 × 不變價／動量／RF・HGB 模式 A・B；數字格為紅色 **TBD** | U |
| `05_conclusion.tex` | 1 句 placeholder | W/X/Y/Z 四段 | W–Z |
| `references.bib` | 1 筆範例（Shannon 1948） | 已查證之真實文獻（AI 與領域約各半） | — |

## 投稿前作者必須處理（論文中以紅字標示）

- [x] `tables/comparison.tex`：已填入 DIC3 封存測試數字（來源：prometheans152/FreshMarketPriceForecastAgent `docs/midterm/public_test_results.json`）。資訊圖表上的數字是錯的（不變價 macro-F1 實為 0.309，不是 0.620），未使用。
- [x] `04_experiments.tex`：日期範圍、τ＝5%、RF/HGB 超參數與 seed 42；原稿的 θ 在 DIC3 系統中不存在，已移除。
- [x] 模式 B 公式、動量基線視窗、0＝缺值：已依 DIC3 程式（`store_adapter.py`、`baselines.py`、`configs/project.yaml`）確認並改寫。
- [x] `main.tex`：作者 Ya-Ting Yu（NCHU CSE, Taichung）與 email 已填（若 ICEIB 採雙盲審查，投稿前需匿名化）。
- [ ] Overleaf 編譯：無錯誤、無 undefined citation、≤ 8 頁。
