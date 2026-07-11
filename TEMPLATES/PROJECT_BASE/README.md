# Project Base Template

這是 Dashboard、Simulator、Operation Tool 與 Hybrid 專案共用的第一版底座。

## 使用方式

- 正式專案應複製這個模板後開發，不要直接在模板內開發。
- 開始時先確認專案類型、商業目的、主要使用者與預期成果。
- 專案涉及 Excel、CSV、Google Sheet、歷史資料、營運資料或其他資料集時，必須先完成 Data Discovery、Analysis Review 與 Gate A、B、C。
- 依照 `docs/PROJECT_STATUS.md` 記錄目前階段、完成 Gate、待確認決策與下一步。
- 重要假設、決策與風險分別記錄在 `docs/DECISIONS.md` 與 `docs/RISKS.md`。

## 基本工作流程

```text
Intake
  -> Data Discovery
  -> Analysis Design
  -> Data Preparation
  -> Product Design
  -> Implementation
  -> Verification
  -> Preview
  -> Release
  -> Continuous Improvement
```

沒有資料的專案可以將 Data Discovery 與 Data Preparation 標記為不適用，但必須在 `PROJECT_STATUS.md` 記錄原因。涉及資料時，不得從原始資料直接跳到視覺化、模擬或正式功能。

## 資料 Gate

- Gate A：使用者確認 AI 對資料、欄位與資料粒度的理解。
- Gate B：使用者確認分析方向、KPI、假設與商業意義。
- Gate C：使用者確認清洗／轉換後的資料可供產品使用。

未經使用者確認，不得自行宣稱 Gate 已通過。若使用者明確要求跳過 Gate，必須記錄決定、原因與風險。

## 目錄用途

- `docs/`：需求、狀態、資料字典、分析、決策、風險與驗收文件。
- `data/raw/`：原始資料；不可覆寫，也不應預設提交 GitHub。
- `data/sample/`：匿名化、虛構或核准的小量測試資料。
- `data/processed/`：由可重複執行流程產生的處理後資料。
- `analysis/scripts/`：可重複執行的分析與資料轉換腳本。
- `analysis/outputs/`：報表、統計結果與中間產物。
- `src/`：應用程式原始碼。
- `tests/`：自動化與手動驗證相關測試。
- `deployment/`：部署、環境與回滾資訊。

## 小型專案原則

可以合併相鄰階段或以較短文件記錄，但不能省略會影響商業意義、資料安全、資料品質或使用者決策的確認。只保留對專案有用的證據，避免為文件而文件。

