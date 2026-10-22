# 安全知識來源與版本查核

每次評估依專案技術從官方頁面確認版本、發布狀態、適用範圍與查核日期。以下網址提供查核入口；引用具體控制項前，開啟該版本原文並核對 ID。無網路時在報告寫「尚未完成即時查核」，並以已取得的資料標示版本來源。

| 來源 | 適用時機與官方入口 |
|---|---|
| OWASP ASVS | Web 應用及相關 API 的技術控制；https://owasp.org/projects/asvs |
| OWASP WSTG | Web 測試方法；https://owasp.org/projects/web-security-testing-guide |
| OWASP MASVS／MASTG | Mobile 要求與測試；https://mas.owasp.org/ |
| OWASP SAMM | 軟體開發成熟度，僅在流程風險與範圍相符時；https://owaspsamm.org/ |
| NIST SSDF | 安全開發流程與供應鏈實務；https://csrc.nist.gov/projects/ssdf/publications |
| NIST SP 800 系列 | 依特定控制需求選篇；https://csrc.nist.gov/publications/sp |
| CWE | 弱點類型分類，搭配專案證據判斷具體漏洞；https://cwe.mitre.org/ |
| CVE／NVD | 已知漏洞識別與產品版本查核；https://nvd.nist.gov/ |
| CISA KEV | 已知遭利用項目的優先排序線索；https://www.cisa.gov/known-exploited-vulnerabilities-catalog |
| CERT/CC | 公告與協調資訊；https://www.kb.cert.org/vuls/ |

語言、框架、OS、套件與雲 SDK 的官方安全文件通常比通用清單更能判斷具體配置。ISO/IEC 27001、27002 可作背景控制參照，但組織合規稽核另行交接。

紀錄格式：`來源名稱｜版本｜stable/draft｜查核日期｜URL｜適用元件｜引用的控制項及原文位置`。草案明確標記為 draft；標準映射先列為待驗證要求，實際測試再依證據判定狀態。若控制項 ID 尚待核對，先記錄控制主題與待查來源。
