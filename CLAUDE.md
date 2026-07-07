# Job — 求職專案（履歷健檢 + 面試準備）

個人求職工作區，與公司 repo（merchant-portal）完全無關。本專案所有產出僅供個人求職使用。

## 資料夾結構

- `resume/` — 履歷原稿與各版本（中文 / 英文；依職缺客製的版本以 `resume/<公司>-<職缺>/` 分資料夾）
- `jd/` — 收集的職缺 JD（一個職缺一個 `.md`，檔名 `<公司>-<職缺>.md`）
- `interview/` — 面試準備產出（STAR 故事庫、模擬題、公司研究筆記）
- `notes/` — 薪資談判、offer 比較等其他筆記

## 專案層級 skills（`.claude/skills/`，來源 [Paramchoudhary/ResumeSkills](https://github.com/Paramchoudhary/ResumeSkills)，2026-07-03 安裝、已安全掃描）

| 用途 | Skill |
|---|---|
| 改履歷 | `resume-ats-optimizer`、`resume-bullet-writer`、`resume-quantifier`、`resume-formatter`、`tech-resume-optimizer` |
| 對職缺客製 | `job-description-analyzer`、`resume-tailor` |
| 面試準備 | `interview-prep-generator`、`salary-negotiation-prep` |

## 工作慣例

- 履歷內容**以事實為準**，不得虛構經歷或數字；量化估算需標註「估算」並與本人確認
- 個資（身分證字號、完整地址、出生年月日）不寫進履歷產出
- 建議流程：JD 進來 → `job-description-analyzer` 算匹配度 → `resume-tailor` 客製 → `resume-ats-optimizer` 健檢 → `interview-prep-generator` 出 STAR 題庫
