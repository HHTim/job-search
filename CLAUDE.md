# Job — 求職專案（履歷健檢 + 面試準備）

個人求職工作區，與公司 repo（merchant-portal）完全無關。本專案所有產出僅供個人求職使用。

## 資料夾結構

- `resume/` — 履歷原稿與各版本，四層架構：
  1. `黃浩庭-master.md` — 完整素材庫（所有專案全細節），不直接拿去投遞，客製時從這裡撈素材
  2. `黃浩庭-onepage.md` — 定稿內容，套用 FAANG 標準（單頁、每職位 3–5 條、XYZ 公式）從 master 篩選而成，**唯一的文字真相來源**，改內容一律先改這裡
  3. `黃浩庭-ats.html` — ATS 投遞版（單欄、無照片、無表格），內容需與 onepage.md 逐字一致
  4. `黃浩庭-rwd.html` — RWD 美化版（含照片、響應式、視覺設計），內容需與 onepage.md 逐字一致
  - **改動 ats.html／rwd.html 的文字後，務必用 grep/diff 跟 onepage.md 核對一致**（無自動化同步機制，曾發生手動編輯造成措辭漂移）
  - 依職缺客製的版本以 `resume/<公司>-<職缺>/` 分資料夾
- `jd/` — 收集的職缺 JD（一個職缺一個 `.md`，檔名 `<公司>-<職缺>.md`）
- `interview/` — 面試準備產出（STAR 故事庫、模擬題、公司研究筆記）
- `notes/` — 薪資談判、offer 比較等其他筆記

## 專案層級 skills（`.claude/skills/`，來源 [Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills)，2026-07-03 安裝、已安全掃描）

| 用途 | Skill |
|---|---|
| 改履歷 | `resume-ats-optimizer`、`resume-bullet-writer`、`resume-quantifier`、`resume-formatter`、`resume-modern`、`tech-resume-optimizer` |
| 對職缺客製 | `job-description-analyzer`、`resume-tailor` |
| 面試準備 | `interview-prep-generator`、`salary-negotiation-prep` |
| HTML／視覺排版設計 | `frontend-design`（來源 [anthropics/claude-code](https://github.com/anthropics/claude-code) plugins/frontend-design，官方 skill，2026-07-11 安裝、內容為純設計指引已檢視無風險） |

## 排版驗證（Playwright）

已安裝 Playwright（裝在 `~/.claude/tools/playwright`，**不在此 repo 內**，避免 node_modules 混進履歷專案），可對 `resume/*.html` 截圖驗證排版與匯出 PDF：
- 截圖：`node ~/.claude/tools/playwright/screenshot.js <html路徑> <輸出資料夾>`（預設輸出手機 390px、桌面 1100px 兩張）
- 截圖存放於 `test_img/`（驗證用，已加入 `.gitignore`，非專案產出，不進 git 歷史）
- 改動 rwd.html／ats.html 排版後，應截圖自行檢查，不要只憑程式碼判斷有沒有問題

## Git

本專案已初始化為 git repo，並推送至 GitHub **Private** repo：https://github.com/HHTim/job-search

- 內含真實姓名、聯絡方式、大頭照等個資，**不得**改為 Public。
- `.gitignore` 已排除 `.DS_Store`、`.gstack/`（工具暫存檔）、`test_img/`（排版驗證截圖）。

## 工作慣例

- 履歷內容**以事實為準**，不得虛構經歷或數字；量化估算需標註「估算」並與本人確認
- 個資（身分證字號、完整地址、出生年月日）不寫進履歷產出
- 建議流程：JD 進來 → `job-description-analyzer` 算匹配度 → `resume-tailor` 客製 → `resume-ats-optimizer` 健檢 → `interview-prep-generator` 出 STAR 題庫
