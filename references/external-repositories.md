# 外部 GitHub 倉庫參考

以下倉庫作為按需研究入口；工具推薦和執行方式由每次專案的證據決定。先按技術、風險與驗證目標選擇來源，再到原倉庫核對目前版本、授權、必要能力、費用、資料流與維護狀態。記錄查核日期和實際採用的頁面；引用標準或控制項時，以官方標準原文為準。借鑑流程與概念；重用第三方文字或程式碼前核對授權條件。

| 倉庫 | 研究用途 | 採用條件與界線 |
|---|---|---|
| [Cloudflare security-audit-skill](https://github.com/cloudflare/security-audit-skill) | 覆蓋紀錄、候選弱點驗證、結構化發現與報告 | 借鑑證據方法；其完整稽核流程需要平行子代理、Node.js 和隔離沙箱，僅在環境具備條件且測試已獲授權時考慮執行。 |
| [GitHub awesome-copilot/security-review](https://github.com/github/awesome-copilot/blob/main/skills/security-review/SKILL.md) | 跨檔資料流、程式碼審查、發現複核 | 可研究整庫或指定路徑的審查方法；依實際技術和證據挑選檢查項目。 |
| [Trail of Bits Skills](https://github.com/trailofbits/skills) | 靜態分析、供應鏈、差異審查等專項方法 | 挑選與專案相符的 Skill；重用內容時核對其授權與平台前提。 |
| [Anthropic Claude Code Security Review](https://github.com/anthropics/claude-code-security-review) | PR 差異審查和發現回報 | GitHub Action 需 Claude API key；採用前評估 PR 來源、提示注入風險、資料流與費用，列為選用整合。 |
| [OpenAI Codex Security](https://github.com/openai/codex-security) | CLI／SDK 掃描、候選驗證和覆蓋報告 | 屬選用的執行工具；先核對登入、模型存取、用量成本、資料處理及執行授權。開源授權與免費掃描分別判斷。 |

研究其他 GitHub 倉庫時，優先查看技術或標準維護者的原始倉庫。例如 [OWASP Cheat Sheet Series](https://github.com/OWASP/CheatSheetSeries) 提供安全實務、[OWASP ASVS](https://github.com/OWASP/ASVS) 提供適用於 Web 的版本化驗證要求；工具候選可從 [OSV-Scanner](https://github.com/google/osv-scanner) 與 [Trivy](https://github.com/aquasecurity/trivy) 等官方倉庫開始。依專案技術繼續尋找其他來源，並用[工具研究與選型](tool-research.md)的欄位比較其實際覆蓋。以上倉庫狀態於 2026-10-22 查核；後續評估以當次查核結果為準。
