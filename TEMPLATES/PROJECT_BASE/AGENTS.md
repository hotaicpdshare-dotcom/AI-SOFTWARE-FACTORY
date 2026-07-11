# Project-Level AI Instructions

這份文件可放入由模板建立的新 repository，讓獨立 repository 不必假設可以直接存取 AI-SOFTWARE-FACTORY。

## Required Reading

開始重要工作前，先閱讀目前專案的文件與規則：

- `docs/REQUIREMENTS.md`
- `docs/PROJECT_STATUS.md`
- `docs/ACCEPTANCE_CRITERIA.md`
- `docs/DATA_DICTIONARY.md`
- `docs/ANALYSIS_REPORT.md`
- `docs/DECISIONS.md`
- `docs/RISKS.md`
- `data/README.md`
- `analysis/README.md`

若專案中另有 Factory 的 `RULES/`、`PROMPTS/` 或 `WORKFLOWS/`，也要閱讀相關文件。至少遵循 `DATA_RULES`、`DATA_DISCOVERY`、`ANALYSIS_REVIEW` 與適用的專案生命週期。

## Project Start Rules

- 先確認 Dashboard、Simulator、Operation Tool 或 Hybrid 類型。
- 先確認商業目的、主要使用者、預期成果與成功標準。
- 修改既有功能前，先理解現況、相依功能與現有決策。
- 不得直接從原始 Excel 或其他原始資料跳到視覺化、模擬或正式功能。
- 涉及資料時，必須先完成 Data Discovery、Analysis Review、資料準備與適用的資料 Gate。
- 若使用者資料尚未確認，不得把 AI 推測當作業務事實。

## Data Rules

- `data/raw/` 的原始資料不可直接覆寫、清洗或取代。
- `data/sample/` 只能放匿名化、虛構或經核准的安全資料。
- `data/processed/` 必須由可重複執行的腳本或明確查詢產生。
- 公司敏感資料、個資、秘密、憑證、金鑰與未去識別化資料不得提交到 GitHub。
- 必須維護資料字典，並記錄資料粒度、缺失值、重複值、型別、日期範圍、唯一值與異常值。
- 必須分開記錄已確認事實、AI 假設與不確定項目。

## Gates and Records

- Gate A：使用者確認 AI 對資料、欄位與一筆資料代表什麼的理解。
- Gate B：使用者確認分析方向、KPI、假設與商業意義。
- Gate C：使用者確認清洗／轉換後資料可供產品使用。
- 必須維護 `docs/PROJECT_STATUS.md`，記錄目前階段、完成狀態、完成 Gate、待確認 Gate 與下一步。
- 所有重要假設與決策寫入 `docs/DECISIONS.md`。
- 所有風險寫入 `docs/RISKS.md`。
- 未經使用者確認，不得自行宣稱 Gate 已通過。
- 若使用者明確要求跳過 Gate，必須在狀態或決策文件記錄跳過原因、使用者決定、風險與緩解方式。

## Engineering Rules

- 先建立最低可用版本，再逐步增加功能。
- 將資料存取、業務邏輯與介面呈現分開。
- 修改後測試主要流程、錯誤流程、空資料與相關既有功能。
- 使用繁體中文作為預設使用者介面語言。
- 不要為小型專案加入沒有明確價值的框架、文件或功能。

## Completion Report

完成工作後回報：

1. 變更摘要
2. 修改檔案
3. 測試結果
4. 部署狀態
5. 已知限制
6. 下一步

