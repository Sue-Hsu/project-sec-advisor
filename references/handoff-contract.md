# SecOrchestrator 交接契約 v1

一份評估產生一份 Markdown 報告及可選的 JSON sidecar，兩者共用 `assessment_id`。同專案重評估使用新 `assessment_id`、保留相同 `project_id` 與既有評估紀錄。JSON 使用 UTF-8、標準語法及去識別化資料，供支援 JSON 的 Agent 讀取。用 [handoff-template.json](../assets/handoff-template.json) 複製欄位骨架；欄位定義以本文件為準。

## 頂層欄位

| 欄位 | 型別／規則 |
|---|---|
| `schema_version` | 字串，固定 `1.0`；重大破壞性更動升主版。 |
| `assessment_id` | 非空字串，單次評估唯一；建議 `PSA-YYYYMMDD-<短識別>`。 |
| `project_id` | 非空穩定專案識別，不含機密或絕對路徑。 |
| `assessment_date` | `YYYY-MM-DD`。 |
| `skill_name` | 固定 `project-sec-advisor`。 |
| `skill_version` | 執行時 SKILL.md 的版本。 |
| `report_path` | 此交接所對應 Markdown 報告的相對路徑或 Vault 路徑；無法持久化時為 `null` 並在限制中說明。 |
| `scope` | 物件：`included`、`excluded`、`source_ref`、`limitations`；前二與限制為字串陣列，`source_ref` 可為 `null`。 |
| `findings` | 陣列，含已確認漏洞、疑似弱點、架構風險。 |
| `unverified_items` | 陣列，含尚未執行或證據不足的要求／檢測。 |
| `cross_domain_referrals` | 陣列，只記交接需求，不假定目標 Skill 存在。 |
| `recommended_follow_up` | 陣列，按優先順序列動作與所需授權。 |
| `evidence_references` | 陣列，集中保存去識別化證據定位。 |

## 子項結構

- `findings[]`：`id`、`component`、`category`（`confirmed_vulnerability`／`suspected_weakness`／`architectural_risk`）、`summary`、`risk_level`、`verification_status`、`evidence_ids`（字串陣列）、`next_action`。只有實測或可直接證明失效的證據才能使用 `confirmed_vulnerability`。`verification_status` 只用 Skill 主文件的五種狀態。
- `unverified_items[]`：`id`、`component`、`requirement`、`reason`、`verification_status`（一般為 `NOT_TESTED` 或 `INCONCLUSIVE`）、`proposed_test_id`（可為 `null`）。
- 報告風險表中類型為「未驗證要求」的列，使用相同 `id` 放入 `unverified_items[]`；`findings[]` 保存其餘三種發現類型。
- `cross_domain_referrals[]`：`id`、`domain`（如 `cloud_account`／`host_os`／`governance`／其他描述）、`reason`、`evidence_ids`、`handoff_question`。
- `recommended_follow_up[]`：`id`、`priority`（`high`／`medium`／`low`）、`action`、`authorization_needed`（布林）。
- `evidence_references[]`：`id`、`kind`（`source`／`config`／`document`／`test`／`official_reference`）、`locator`、`observed_at`、`summary`。`locator` 使用去識別化的相對路徑與行號或公開 URL；以摘要取代金鑰與私密內文。

每次交接保留全部頂層欄位，允許各陣列為空。項目 `id` 在單次評估內唯一；`evidence_ids` 對應 `evidence_references[].id`。報告中使用相同 ID，讓不同 Agent 能反查。若有未查證來源或能力限制，寫入 `scope.limitations`；空陣列只表示本次範圍沒有對應紀錄。
