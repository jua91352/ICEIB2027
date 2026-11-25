# A2Z 論文寫作 SOP — 參考對照表

來源：`A2Z outline example.pdf`（老師提供，2020 A–Z SOP）。
本檔把每個字母查核點整理成「意思 → 本論文寫在哪裡」，供 Agent（Claude Code / Antigravity + Overleaf MCP）與作者逐點核對。
`.tex` 原始碼中以 `% A`、`% G`、`% PA` 等註解標示對應位置（PDF 上看不到）。

## Abstract（A–F）→ `latex/sections/00_abstract.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| A | Attention Getter：動機與引題 | 颱風／豪雨後菜價暴漲，消費者看到今天店價卻無法判斷未來 |
| B | But：挑戰 | 公開均價 ≠ 店價；價格多數不變、少數大變；LLM 可能亂報數字 |
| C | Cure：提出的解法 | 提出 FMPA（Fresh Market Price Forecast Agent） |
| D | Development：方法設計 | LLM 只做意圖解析與解釋；MCP 工具取數；RF（7 天）/ HGB（14 天）；A/B 模式 |
| E | Experiments：實驗 | 臺中市 13 個公有市場、防洩漏時間切分、不變價與動量基線、macro-F1 與 MAE |
| F | Findings：結果 | 模型未勝簡單基線 → 定位為透明的現價錨定決策輔助 |

## I. Introduction（G–L）→ `latex/sections/01_introduction.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| G | General：現況（含客觀數據） | 官方批發行情與颱風後菜價統計 |
| H | However：挑戰（比 B 更完整） | 三個挑戰：均價≠店價、價格黏性、LLM 幻覺 |
| I | In literature：文獻中的解法（由舊到新、由簡到繁） | 統計 → 樹模型 → 深度學習 → LLM Agent |
| J | Judgement：評論各類方法優缺點 | 各類方法的限制 |
| K | Keypoint：設計精神、novelty、貢獻 | RQ1–RQ3、貢獻 C1–C3 |
| L | List the organization：文章結構 | 以 `\ref` 交代各節 |

## II. Related Work（M–O）→ `latex/sections/02_related_work.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| M | Methods：文獻分類 | II-A AI 技術、II-B 領域知識（各約一半） |
| N | New proposed：新趨勢與本文新意 | II-D Research Gap → Our Project |
| O | Organize：SWOT／比較表歸納 | Table I：8 欄 Article Summary Table |

## III. Proposed Scheme（PA–PM）→ `latex/sections/03_proposed_scheme.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| PA | Aim：目標 | III-A Design Aim |
| PB | Based on／背景／聚焦 | III-B 五個領域核心思維 M1–M5 |
| PC | Cure：解法與有效的原因 | 每個 M 對應一個系統元件 |
| PD | Design：架構設計 | III-C System Architecture |
| PE | Paper elements：有哪些元件 | 模組 ①–⑤ |
| PF | Formulation／Foundation | III-D 公式 (1)–(3)、Table II 符號表 |
| PG | Graph：架構圖說明 | Fig. 1 |
| PH | How：如何達成設計目標 | III-E 流程說明 |
| PI | Implementation：流程圖／偽碼 | Fig. 2、Algorithm 1 |
| PJ | Jump to an example | 青蔥 NT$380 範例（示意，非實驗結果） |
| PK | Key points contribution | III-F Key Points |
| PL | Later how to do simulation | 銜接 Section IV |
| PM | Math proof | 本文為應用系統，無定理證明；以公式定義取代 |

## IV. Simulation（Q–V）→ `latex/sections/04_experiments.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| Q | Quality & Quantity：指標 | direction macro-F1、relative-change MAE |
| R | Related methods to compare | 不變價、動量基線 |
| S | Simulation setup | 資料、時間切分、標籤成熟度防洩漏 |
| T | Tuning parameters | RF/HGB、α = 0.3、θ |
| U | Useful results | Table III（數字待作者核對填入） |
| V | Verify effectiveness | Discussion：為何基線難贏、RQ1–RQ3、效度威脅 |

## V. Conclusion（W–Z）→ `latex/sections/05_conclusion.tex`

| 代號 | 意思 | FMPA 論文內容 |
|---|---|---|
| W | What proposed：回顧動機與挑戰 | 第一段 |
| X | eXcel：適用情境與優點 | 第二段 |
| Y | Yields：產出與結果 | 第三段（含負向結果） |
| Z | Zen：結論與未來工作 | 第四段（同店實價配對驗證等） |
