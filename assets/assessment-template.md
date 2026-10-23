# 專案資安評估與測試計畫：<project_id>

- Assessment ID：<assessment_id>
- 評估日期：<YYYY-MM-DD>
- Skill：project-sec-advisor <version>
- 範圍與本次來源快照：<included / excluded / commit SHA、發行物雜湊或 unknown；dirty 狀態>
- 評估類型：<初次評估／增量評估／廣範圍複查>
- 前次基準：<assessment_id、固定來源快照、報告參照；初次評估填不適用>
- 評估模式：分析與規劃；實際執行項目：<無或列出授權測試>
- 能力限制／尚未完成即時查核：<列出>
- 對應交接檔：<相對路徑或未建立>
- 歸檔狀態與位置：<已保存的相對路徑／Vault 路徑；或未持久歸檔及原因>

## 決策摘要

<3–5 行：主要風險、最優先的檢查、仍未驗證的事項；明確區分計畫與已完成測試>

## 1. Project Overview

<用途、使用者、部署／執行形態、已知限制>

## 2. Technology Inventory

| 元件 | 技術與版本 | 實際用途 | 證據 ID／位置 | 信心／未知 |
|---|---|---|---|---|
| <component> | <technology> | <usage> | <E-001> | <confirmed / inferred / unknown> |

## 3. Architecture & Data Flow

<資產、資料流、外部依賴、身分與信任邊界；可放 Mermaid，未知明列>

## 4. Security Scope

- 包含：<項目>
- 排除：<項目與理由>
- 環境／授權：<現況>

### 基準與變更影響（增量評估時填寫）

- 基準涵蓋與限制：<前次受測範圍、環境、測試證據及未驗證項目；缺少基準時說明>
- 比較範圍：<基準與本次 commit／PR、其他固定版本識別；dirty 狀態與限制>

| 變更／證據 ID | 直接改動 | 連動元件、功能或資料流 | 影響判斷與未知處 |
|---|---|---|---|
| E-001 | <改動> | <呼叫者、依賴者、共用控制或信任邊界> | <理由及證據> |

| Test ID／風險 ID | 本次安排 | 選擇或延後理由 | 涵蓋缺口 |
|---|---|---|---|
| T-001 | <選入／延後／擴大人工審查> | <與變更或基準的關係> | <尚未驗證的部分> |

- 廣範圍複查觸發條件與建議時點：<本次是否觸發、理由及下次節點>
- 基準更新判斷：<本次是否具有固定快照、範圍及實測證據；可供後續沿用的涵蓋範圍>

## 5. Threat & Risk Assessment

| ID | 元件／資產 | 類型 | 威脅路徑與影響 | 風險 | 證據 ID | 驗證狀態 | 下一步 |
|---|---|---|---|---|---|---|---|
| F-001 | <component> | <已確認漏洞／疑似弱點／架構風險／未驗證要求> | <具體路徑> | <等級與理由> | E-001 | NOT_TESTED | <action> |

## 6. Applicable Security Standards

| 標準／官方指引 | 版本與狀態 | 查核日期 | 適用元件／要求 | 原始 URL | 控制項 ID 查核狀態 |
|---|---|---|---|---|---|
| <source> | <stable/draft> | <date 或尚未完成即時查核> | <why> | <URL> | <verified / omitted> |

## 7. Recommended Free Tools

| 類別 | 工具／官方來源 | 查核日期／版本／維護狀態 | 免費／授權限制 | 適用理由 | 能測與盲點 | 平台／CLI／依賴 | 外傳／帳號／副作用 | 分級 |
|---|---|---|---|---|---|---|---|---|
| <method> | <tool + URL> | <date / version / status> | <terms> | <reason> | <coverage / gap> | <requirements> | <privacy / side effects> | <必要／建議／選用／不適用> |

### 入選工具的本機現況（按需）

列出計畫使用的工具。未進行本機查詢時標示「未查證」；搜尋不到時標示「未找到」，並保留查詢範圍。

| 工具 | 本機狀態 | 版本／確認方式 | 取得方式或替代方案 | 待確認事項 |
|---|---|---|---|---|
| <tool> | <已確認可用／未找到／未查證> | <版本與不啟動執行檔的證據；或未查證> | <官方來源或人工替代> | <授權／來源／版本等> |

## 8. Tool Coverage Matrix

| 安全要求／風險 ID | 工具可直接驗證 | 僅提供線索 | 人工測試／未涵蓋 | 原因 |
|---|---|---|---|---|
| <F-001> | <tool or none> | <tool or none> | <method> | <gap> |

## 9. Security Testing Plan

| Test ID | 目標 | 方法／工具 | 前置條件與授權範圍 | 預期證據 | 驗收準則 | 副作用／停止條件 |
|---|---|---|---|---|---|---|
| T-001 | <goal> | <method> | <environment> | <artifact> | <criterion> | <limit> |

### 執行前提與待確認事項

| Test ID | 網路需求 | 原始碼／資料是否外傳 | 預估耗時與依據 | 阻塞問題與需要誰確認 |
|---|---|---|---|---|
| T-001 | <無／有／未查證> | <無／有／未查證及去向> | <估計或無法估計；註明依據> | <測試環境、帳號、範圍等> |

## 10. Verification Matrix

| Test ID | 狀態 | 實際執行日期／環境 | 證據 ID | 判定理由 |
|---|---|---|---|---|
| T-001 | NOT_TESTED | 未執行 | 無 | 僅完成計畫 |

## 11. Unverified Risks

<未執行檢測、缺少資料、無法由免費工具充分驗證之事項與影響>

## 12. Cross-Domain Referrals

| ID | 領域 | 發現與證據 ID | 為何交接 | 待回答問題 |
|---|---|---|---|---|
| R-001 | <cloud_account / host_os / governance> | <E-001> | <reason> | <question> |

## 13. References & Evidence

| Evidence ID | 類型 | 去識別化位置／URL | 觀察日期 | 觀察摘要 |
|---|---|---|---|---|
| E-001 | <source / config / document / test / official_reference> | <relative path:line or URL> | <date> | <summary> |

> 報告以已檢視範圍和實際證據為準；`NOT_TESTED` 保留待測狀態，工具零發現只記錄該次檢測的覆蓋與限制。
