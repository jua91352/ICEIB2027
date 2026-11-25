# ICEIB 2027 — FMPA 會議論文（AIoT DIC4）

把 DIC3 期末專題 **FMPA（Fresh Market Price Forecast Agent，生鮮市場價格預測代理）** 改寫成 ICEIB 2027（IEEE track）會議論文初稿。
論文以 Overleaf 撰寫（Agent + Overleaf MCP 編輯 LaTeX），改寫過程用 **OpenSpec** 規格管理。

> 論文標題：*FMPA: A Store-Price-Anchored Domain AI Agent for 7- and 14-Day Fresh Vegetable Price Forecasting*

## DIC4 繳交項目對照

| 老師要求（白板） | 本 repo 位置 |
|---|---|
| ① Overleaf 投稿 draft（Agent + Overleaf MCP，LaTeX） | [`latex/`](latex/)（Overleaf 工作版本） |
| ② 套 OpenSpec（投稿 Abstract / Intro / Related …） | [`openspec/`](openspec/) |
| 繳交 1：Overleaf paper **修改前 / 修改後** | [`paper/before/`](paper/before/)、[`paper/after/`](paper/after/)，對照表見 [`paper/README.md`](paper/README.md) |
| 繳交 2：OpenSpec 放 GitHub — **goal / design / tasks.md** | [`proposal.md`](openspec/changes/draft-iceib2027-fmpa-paper/proposal.md)（Goal / Why）、[`design.md`](openspec/changes/draft-iceib2027-fmpa-paper/design.md)、[`tasks.md`](openspec/changes/draft-iceib2027-fmpa-paper/tasks.md)、[`specs/`](openspec/changes/draft-iceib2027-fmpa-paper/specs/) |

## Workflow（題目 → 發展）

1. **DIC3 資料**（iLearning）→ [`AIoT-DIC3-ProjectRefactor/`](AIoT-DIC3-ProjectRefactor/)
2. **Overleaf 帳號** → 講義 Step 1：New Project → **Upload Project**，上傳 `paper/before/FMPA-ICEIB2027-before.zip`（老師模板＝修改前）
3. **ChatGPT / Antigravity / Claude Code** → 讀 `myRef/` 與 DIC3 資料，產生 OpenSpec change 與 `latex/` 論文
4. **Agent 加入 Overleaf MCP** → 講義 Step 2：Overleaf Git 網址 + Git token → 執行 `setup_overleaf_mcp.ps1`（clone 到 `%USERPROFILE%\overleaf-projects\<資料夾>`，`uvx mcp-server-git` 註冊成 Claude Code MCP）→ Agent 把 `latex/` 寫進 clone、commit、push 回 Overleaf（修改後）

### Overleaf 為什麼一定要有 `main.tex`？

Overleaf 專案的**根目錄**必須有主檔（`main.tex`，含 `\documentclass`）。所以上傳到 Overleaf 的是 `latex/` 的內容（或 `paper/*/` 裡的 zip，zip 根目錄就是 `main.tex`），**不要上傳整個 ICEIB2027 資料夾**——它的根目錄是作業 repo，不是 LaTeX 專案。GitHub Sync 不是必要的；講義用的是 Overleaf 的 Git integration。

## 資料夾結構

```text
ICEIB2027/
├── .claude/                      # OpenSpec 產生的 Claude Code 指令與 skills（/opsx:propose、/opsx:apply…）
├── AIoT-DIC3-ProjectRefactor/    # DIC3 專題說明（FMPA README）
├── ICEIB paper/                  # 會議官方/原始 IEEE 模板 zip（修改前的來源）
├── latex/                        # Overleaf 論文工作版本（main.tex、sections/、figures/、tables/、references.bib）
├── myRef/                        # 參考資料
│   ├── A2Z outline example.pdf   #   ① 老師的 A2Z SOP
│   ├── A2Z-SOP-reference.md      #   A2Z 查核點 → 本論文章節對照
│   ├── FMPA 專題簡報解析.pdf      #   ② 你的解析
│   ├── FMPA專題簡報系統性解析資訊圖表.png
│   ├── ICEIB2027-conference-info.md  # ③ 會議資訊（Conf. information）
│   ├── 期末專題提案作業規範.pdf
│   └── README.md
├── openspec/
│   ├── config.yaml               # 專案脈絡與撰寫規則
│   ├── changes/draft-iceib2027-fmpa-paper/
│   │   ├── proposal.md           # Goal / Why / What Changes / Capabilities / Impact
│   │   ├── design.md             # 寫作與工作流決策、風險
│   │   ├── tasks.md              # 依章節分組的任務清單
│   │   └── specs/paper-*/spec.md # 7 個章節規格（SHALL + Scenario）
│   └── specs/                    # archive 後的正式規格
├── paper/
│   ├── before/                   # 修改前（原始模板）
│   ├── after/                    # 修改後（FMPA 初稿快照）
│   └── README.md                 # 逐節修改對照
├── temp_instructions.json        # `openspec instructions proposal --json` 輸出
└── temp_spec_inst.json           # `openspec instructions specs --json` 輸出
```

## OpenSpec 使用方式

需要 `@fission-ai/openspec`（本專案以 1.2.0 建立）。

```bash
openspec list                                   # 列出 change
openspec show draft-iceib2027-fmpa-paper        # 檢視 change
openspec validate draft-iceib2027-fmpa-paper --strict
openspec status --change draft-iceib2027-fmpa-paper
```

在 Claude Code 中可用 `/opsx:apply` 繼續完成 `tasks.md` 剩下的任務，完成後 `/opsx:archive` 把規格併入 `openspec/specs/`。

> 注意：若 repo 放在名稱含括號的路徑（例如 `week 12(DIC4)`），`openspec status` 會把 specs 誤判為未完成（glob 被括號干擾）；`openspec validate` 不受影響。放在一般路徑即可正常顯示。

## 目前狀態

- 已完成：OpenSpec 規格（proposal / specs / design / tasks，`validate --strict` 通過）、六個章節 LaTeX、TikZ 架構圖與流程圖、8 欄文獻摘要表、修改前/後快照。
- 待作者完成（論文中以紅字 **TODO / TBD** 標示）：DIC3 實驗正式數字、日期範圍與參數、模式 B 公式確認、作者資訊、Overleaf 編譯與頁數檢查。詳見 [`tasks.md`](openspec/changes/draft-iceib2027-fmpa-paper/tasks.md) 第 6、8 節。

## AI 使用揭露

本 repo 的 OpenSpec 文件、LaTeX 初稿與文獻查證由 AI 助手（Claude Code）協助完成；所有內容需經作者確認。論文 Acknowledgment 中亦有揭露。
