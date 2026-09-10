# CASE_LOCK — 带教者来源与事实账本（空模板）

复制到当前使用者私人空间填写，不写回公开安装目录。账本是可审计的数据，不是隐藏思维链；首轮不展示含答案字段。unknown 不代表正常，null 不代表0。

## 来源锁

- schema_version: 0.2
- case_id: unknown（中性稳定别名，不含诊断）
- lock_revision: 0
- phase: sourcing
- record_type: real-published（仅通过来源准入后可用）
- domain: unknown（msk / stroke）
- training_scope: unknown（full / assessment-only）
- title / authors / year / journal: unknown
- publication_type / peer_review_status: unknown
- pmid / pmcid / doi: unknown（not-assigned 仅在已确认未分配时使用）
- canonical_url / case_page_url: unknown
- article_version / correction_or_retraction_check: unknown
- accessed_at / actual_read_scope / inaccessible_sections: unknown
- patient_key: unknown（原文 Patient 1 等，单病例也明确 single-patient）
- supplemental_sources_same_case: []
- provenance_verified: false
- eligible_for_real_case: false
- source_selection_reason: unknown

## 首轮资料（只填原文支持的条目并关联 fact_id）

| 字段 | 原文值/忠实释义 | fact_id |
| --- | --- | --- |
| 年龄/性别 | unknown | unknown |
| 职业/运动/主要功能背景 | unknown | unknown |
| 主诉/病程 | unknown | unknown |
| 立即影响安全的已知限制（若有） | unknown | unknown |

不能为了凑模板补职业或患者原话。未报告字段可在学员开场省略。

## 事实账本

| fact_id | patient_key | timepoint | item / scale_version | value | unit | side | conditions | status | source_locator |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |

status: reported / not-reported / not-accessed / ambiguous / conflicted。
source_locator 使用页码、章节、段落、表格行/列或图注；未报告项记实际检查过的范围。每个不同时间点单独一行；所有数值保留原单位，不默认疼痛是VAS还是NRS、Berg满分或FMA总分/分项。

## 原作者解释与结局（按请求揭示）

| interpretation_id | 作者诊断/机制主张/干预理由 | 关联事实 | 定位 | 未证实之处 |
| --- | --- | --- | --- | --- |

作者干预、剂量、复测和结局仍逐项进入事实账本，另分组为 author_intervention / author_outcome，不能提前展示。

## 对话状态（可变；不得覆盖固定事实）

- revealed_fact_ids: []
- learner_requests: []（turn_id、请求、响应事实ID或缺失状态）
- learner_hypotheses: []（turn_id、假设、支持/反对、修订；不是病例事实）
- interventions_proposed: []
- retest_and_progression_proposed: []
- hints: []（是否用户请求）
- unresolved_risks: []（未知不等于已排除）
- reveal_authorized: false
- reveal_trigger_quote: null
- completion_status: not-started
- save_status: session-only

## 修订与恢复

| revision | 变动原因 | affected_fact_ids | 旧值/新值与原文定位 | 受影响的点评/日志 |
| --- | --- | --- | --- | --- |

锁定后只能有来源地补充、纠错或标冲突；换患者必须新建Case ID。恢复时核对病例身份、版本、最后阶段及已揭示项，读不回就暂停。
