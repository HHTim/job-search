# Job — 求職專案

黃浩庭（Tim Huang）的個人求職工作區：履歷健檢、職缺客製、面試準備。所有內容僅供本人求職使用，與任何公司內部 repo 無關。

本 repo 為 **Private**：https://github.com/HHTim/job-search

## 資料夾結構

| 資料夾 | 內容 | 目前狀態 |
|---|---|---|
| `resume/` | 履歷原稿與匯出版本 | 有內容（見下） |
| `jd/` | 收集的職缺 JD，一職缺一個 `.md` | 空，待收集 |
| `interview/` | STAR 故事庫、技術面試手冊、公司研究筆記 | 有 `STAR-故事庫.md`、`面試完全準備手冊.md`、`Session交接報告.md` |
| `notes/` | 薪資談判、offer 比較等筆記 | 空，待產出 |
| `.claude/skills/` | 專案層級 Claude Code skills | 11 個（見下） |

### `resume/` 目前檔案

四層架構，內容由上往下衍生，**`黃浩庭-onepage.md` 是唯一的文字真相來源**：

| 檔案 | 用途 |
|---|---|
| `黃浩庭-master.md` | 完整素材庫（所有專案全細節），不直接投遞，客製職缺時從這裡撈素材 |
| `黃浩庭-onepage.md` | 定稿內容，套用 FAANG 履歷標準（單頁、每職位 3–5 條 bullet、XYZ 公式）從 master 篩選而成 |
| `黃浩庭-ats.html` | ATS 投遞版：單欄、無照片、無表格，內容需與 onepage.md 逐字一致 |
| `黃浩庭-rwd.html` | RWD 美化版：含照片、響應式、視覺設計（系統架構藍圖風格），內容需與 onepage.md 逐字一致 |
| `Huang_HaoTing_Resume.pdf` | 由 ats.html 匯出，實際投遞用（ATS 慣例英文檔名） |
| `黃浩庭-履歷.pdf` | 由 rwd.html 匯出，人眼展示／列印用 |
| `photo.jpg` | 履歷大頭照，僅 rwd.html 使用 |

**改動 ats.html／rwd.html 的文字內容後，務必跟 onepage.md 做 grep/diff 核對一致**——目前沒有自動化同步機制，曾發生手動編輯造成措辭漂移。

依職缺客製的版本另建 `resume/<公司>-<職缺>/` 子資料夾（目前尚未建立任何客製版本）。

### `interview/` 目前檔案

| 檔案 | 用途 |
|---|---|
| `STAR-故事庫.md` | 從本人履歷（master/onepage.md）展開的 STAR 故事，通用行為面試用 |
| `面試完全準備手冊.md` | 特定職缺（SI／顧問公司，SA+PG+講師複合角色）的技術面試題庫：系統設計、資料庫正規化、Java 筆試、演算法、Memory Cache、分散式情境。**規則：隨時更新、單一檔案不分拆、上機考題目中英對照**——新面試資訊進來直接併入既有章節，不另開新檔 |
| `Session交接報告.md` | 上述手冊的產出脈絡與待辦事項記錄，非面試素材本身 |

### 排版驗證（Playwright）

已安裝於 `~/.claude/tools/playwright`（**不在此 repo 內**，避免 node_modules 混進履歷專案）。用途：對 `resume/*.html` 截圖驗證排版、匯出 PDF。截圖輸出至 `test_img/`（已加入 `.gitignore`，純驗證用不進 git 歷史）。

## 可用 Skills（`.claude/skills/`）

| 用途 | Skill | 來源 |
|---|---|---|
| 改履歷 | `resume-ats-optimizer`、`resume-bullet-writer`、`resume-quantifier`、`resume-formatter`、`resume-modern`、`tech-resume-optimizer` | [Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills)，2026-07-03 安裝、已安全掃描 |
| 對職缺客製 | `job-description-analyzer`、`resume-tailor` | 同上 |
| 面試準備 | `interview-prep-generator`、`salary-negotiation-prep` | 同上 |
| HTML／視覺排版設計 | `frontend-design` | [anthropics/claude-code](https://github.com/anthropics/claude-code) plugins/frontend-design，官方 skill，2026-07-11 安裝、已檢視內容無風險 |

建議流程：JD 進來 → `job-description-analyzer` 算匹配度 → `resume-tailor` 客製 → `resume-ats-optimizer` 健檢 → `interview-prep-generator` 出 STAR 題庫。

## Git 慣例

```powershell
git add <檔案>
git commit -m "說明變更內容"
git push
```

- Repo 為 Private，內含真實姓名、聯絡方式、大頭照，**不要**改成 Public。
- `.gitignore` 已排除 `.DS_Store`、`.gstack/`（工具暫存檔）、`test_img/`（排版驗證截圖，非專案內容）。
