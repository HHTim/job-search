# Job — 求職專案

黃浩庭（Tim Huang）的個人求職工作區：履歷健檢、職缺客製、面試準備。所有內容僅供本人求職使用，與任何公司內部 repo 無關。

本 repo 為 **Private**：https://github.com/HHTim/job-search

## 資料夾結構

| 資料夾 | 內容 | 目前狀態 |
|---|---|---|
| `resume/` | 履歷原稿與匯出版本 | 有內容（見下） |
| `jd/` | 收集的職缺 JD，一職缺一個 `.md` | 空，待收集 |
| `interview/` | STAR 故事庫、模擬題、公司研究筆記 | 空，待產出 |
| `notes/` | 薪資談判、offer 比較等筆記 | 空，待產出 |
| `.claude/skills/` | 專案層級 Claude Code skills | 10 個（見下） |

### `resume/` 目前檔案

- `黃浩庭-master.md` — 履歷主稿（Markdown）
- `黃浩庭-modern.html` / `黃浩庭-modern-print.html` — 網頁版／列印版排版
- `黃浩庭.pdf` / `黃浩庭-modern-print.pdf` — PDF 匯出
- `Huang_HaoTing_Resume.pdf` — 英文檔名版 PDF（供海外/英文職缺投遞）
- `photo.jpg` — 履歷大頭照

依職缺客製的版本另建 `resume/<公司>-<職缺>/` 子資料夾（目前尚未建立任何客製版本）。

## 可用 Skills（`.claude/skills/`）

來源：[Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills)，2026-07-03 安裝、已安全掃描。

| 用途 | Skill |
|---|---|
| 改履歷 | `resume-ats-optimizer`、`resume-bullet-writer`、`resume-quantifier`、`resume-formatter`、`resume-modern`、`tech-resume-optimizer` |
| 對職缺客製 | `job-description-analyzer`、`resume-tailor` |
| 面試準備 | `interview-prep-generator`、`salary-negotiation-prep` |

建議流程：JD 進來 → `job-description-analyzer` 算匹配度 → `resume-tailor` 客製 → `resume-ats-optimizer` 健檢 → `interview-prep-generator` 出 STAR 題庫。

## Git 慣例

```powershell
git add <檔案>
git commit -m "說明變更內容"
git push
```

- Repo 為 Private，內含真實姓名、聯絡方式、大頭照，**不要**改成 Public。
- `.gitignore` 已排除 `.DS_Store`、`.gstack/`（工具暫存檔，非專案內容）。
