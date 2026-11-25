## 1. 準備（Setup）

- [x] 1.1 凍結修改前版本：原始模板 zip 放入 `ICEIB paper/`，解開後複製到 `paper/before/`
- [x] 1.2 建立 `latex/` 工作版本（由模板複製），`main.tex` 加入 `tikz`、`tabularx`、`array` 套件與 `\cnum`、`\todo` 巨集
- [x] 1.3 整理參考資料到 `myRef/`：A2Z outline、`A2Z-SOP-reference.md`、FMPA 解析 PDF、資訊圖表、會議資訊
- [x] 1.4 把 DIC3 專題說明放到 `AIoT-DIC3-ProjectRefactor/`
- [x] 1.5 更新 `main.tex` 標題為 FMPA 論文標題，作者欄保留待填註記

## 2. Abstract（A–F）

- [x] 2.1 依 A→F 順序撰寫摘要，每句前加 `% A`…`% F` 註解
- [x] 2.2 確認摘要 150–250 字、無引用、縮寫首次出現有全名、明寫「未勝基線」
- [x] 2.3 撰寫 5–6 個 IEEE keywords（AI + 領域）

## 3. I. Introduction（G–L）

- [x] 3.1 G：以官方統計／報告引題（颱風後菜價、消費者物價）
- [x] 3.2 H：價格「多數不變、少數大變」、公開均價 ≠ 店價、LLM 會幻覺數字
- [x] 3.3 I + J：既有方法分類（統計 → ML → DL → LLM Agent）與優缺點評論
- [x] 3.4 K：寫出 RQ1–RQ3 與貢獻 C1–C3（逐條對應 RQ）
- [x] 3.5 L：文章結構段落，全部用 `\ref`

## 4. II. Related Work（M–O）

- [x] 4.1 查證並寫入 `references.bib`（AI 與領域約各半，含 2024–2026 文獻），刪除範例 `shannon1948`
- [x] 4.2 M（AI）：價格預測 ML/DL、簡單基線難以超越、LLM Agent／工具使用／MCP
- [x] 4.3 M（Domain）：零售價格黏性、價格傳遞不對稱、天候衝擊、公開價格資料
- [x] 4.4 O：8 欄 Article Summary Table（`tables/article_summary.tex`，`table*`，≥6 列，≥2 列為 2024 年後）
- [x] 4.5 N：Existing Research → Limitations → Research Gap → Our Project，列出三個缺口並對應方法元件

## 5. III. Proposed Scheme（PA–PM）

- [x] 5.1 PA–PC：設計目標、設計原則（由 5 個核心思維 M1–M5 轉換）、解法說明
- [x] 5.2 PD–PE / PG：TikZ 架構圖 `figures/architecture.tex`（模組 ①–⑤）並逐一說明
- [x] 5.3 PF / PJ：符號表 `tables/notation.tex`、A 模式與 B 模式公式（α = 0.3）、以青蔥為例的計算
- [x] 5.4 PH–PI：TikZ 流程圖 `figures/flowchart.tex`（含資料檢查失敗分支）
- [x] 5.5 PI：Algorithm 1（帶行號；預測值只來自 ForecastEngine 工具）
- [x] 5.6 PK–PL：重點貢獻與如何評估的銜接段落

## 6. IV. Evaluation（Q–V）

- [x] 6.1 S：資料（臺中市 13 個公有市場、n = 2,085 / 1,859）、時間切分、標籤成熟防洩漏規則、軟體
- [x] 6.2 Q + R：指標公式（direction macro-F1、relative-change MAE）與基線（不變價、動量）
- [x] 6.3 T：參數設定（7 天 RF、14 天 HGB、B 模式 α = 0.3 固定不調）
- [x] 6.4 U：結果表 `tables/comparison.tex`，數值格先放紅色 `\todo`
- [x] 6.5 V：討論——為何簡單基線難贏（價格黏性）、A/B 模式意義、RQ3 原型可行性
- [ ] 6.6 （作者）從 DIC3 實驗紀錄核對並填入 macro-F1 / MAE 實際數字，移除所有 `\todo`

## 7. V. Conclusion（W–Z）

- [x] 7.1 W/X/Y/Z 四段：回顧、適用情境、產出（含負向結果）、限制與未來工作
- [x] 7.2 確認結論沒有出現 Section IV 以外的新數字或新引用
- [x] 7.3 加入 AI 使用揭露（Acknowledgment）

## 8. 驗收與交付

- [x] 8.1 靜態檢查：每個 `\cite` 都在 bib、每個 `\ref` 都有 `\label`、括號成對
- [x] 8.2 快照修改後版本到 `paper/after/` 並打包 zip；`paper/README.md` 寫修改前/後對照表
- [x] 8.3 `openspec validate draft-iceib2027-fmpa-paper --strict` 通過
- [x] 8.4 Overleaf 編譯（專案 FMPA-ICEIB2027-after）：0 errors、0 warnings、無 undefined citation、6 頁（≤ 8）
- [ ] 8.5 （作者）Overleaf 下載 PDF 存為 `paper/before/before.pdf` 與 `paper/after/after.pdf`，並截圖修改前/後
- [ ] 8.6 （作者）填入作者姓名、單位、email
- [x] 8.7 推送到 GitHub `jua91352/ICEIB2027`（2026-11-25）

## 9. Overleaf + MCP（講義 Step 1、Step 2）

- [x] 9.1 安裝 `uv`（uvx）與 Claude Code CLI（`claude`），老師的部署腳本需要這兩個指令
- [x] 9.2 Overleaf 專案「DIC4」＝上傳老師模板 `ICEIB2027-IEEE.zip`（修改前）
- [x] 9.3 產生 Overleaf Git token；Git 網址 `https://git@git.overleaf.com/<DIC4 專案 ID>`
- [x] 9.4 Overleaf 免費方案回 "no git access"，無法 clone → 依講義「local folder connect to MCP」改用本機資料夾 `%USERPROFILE%\overleaf-projects\fmpa-paper`（git init：commit 1 = 模板／修改前，commit 2 = FMPA／修改後），以 `uvx mcp-server-git` 註冊為 Claude Code MCP `overleaf-fmpa-paper`（`claude mcp list` 顯示 ✔ Connected）
- [x] 9.5 Overleaf → New project → Existing project (.zip) 上傳修改後 zip（專案 FMPA-ICEIB2027-after），Recompile 0 errors；Agent 在 Overleaf 編輯器修正標題換行並重新編譯
