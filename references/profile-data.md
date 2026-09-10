# Personal Clinical Reasoning Profile — v0.2 数据约定

运行于宿主可读写的私人空间。公开模板为空，不自动建外部数据库，不自动训练模型；隔离由宿主实际实现。读写遵循 therapist-memory.md 与已有授权。拒绝长期记忆不影响任何模式。

## 数据组织

- `PERSONAL_PROFILE.json`：稳定英文键、中文或其他语言值；profile_id为非实名别名；schema_version、revision、updated_at、memory标明版本/保存状态。
- `TRAINING_LOG.json`：一例一次完成记录，包含来源键、学习行为和证据限制；实际记录不进公开项目。
- JSON与旧THERAPIST_PROFILE.md是两种表现形式，不维护两个未经同步的真相。宿主不能可靠JSON写入时用Markdown。选一个canonical_format并记录修订。
- null=未知；[]=尚无条目，不建“unknown技术”的假记录。示范数据不默认注入当前用户画像。

## 核心字段

context保存main_practice、clinical_population、reasoning_style。preferred_assessments、preferred_techniques、frequently_used_exercises保存具体对象及情境。reasoning_observations按strengths、possible_biases、differential_diagnosis、risk_screening、load_design、functional_training、reassessment分类，每项有观察依据。

`knowledge_sources`继续区分available、accepted、applied、preferred，记录actual_read_scope；上传不等于认可，练习不等于真实应用。current_learning_topics、development_areas、next_training_targets记录未来可观察练习目标。

## 每个偏好/观察条目

必备：id、claim、context、source_type(stated/observed)、support_event_ids、counterexample_event_ids、practice_type(real-case-training/fictional-training/actual-clinical/self-report)、preference_confidence(low/medium/high)、last_confirmed。support_event_ids去重，同病例多轮不增加独立支持数。

偏好保留原低/中/高约定；它不是疗效证据。强项/偏差条目另记observation_confidence、recording_gap、alternative_explanation，先区分“未记录”还是“未评估”。稀疏记录只能形成候选观察，不评价执业能力。

## 技术证据A/B/C/D

评估单位是“某技术对特定人群、目标、剂量和情境的具体主张”，不是给整流派贴永久标签。每项独立有evidence字段：category、claim_scope、rationale、sources、reviewed_at、verification_status、limitations；查不到则unknown。

| category | 行动 |
| --- | --- |
| A | 相应情境有较充分支持，继续强化；保留适用范围与局限，不等于正式GRADE高等级 |
| B | 有一定临床价值但证据有限，保留并说明不确定，以复测和功能目标约束 |
| C | 主要个人经验，标个人偏好，不冒充普遍事实，也不自动判无效 |
| D | 与可核实证据明显冲突或有明确风险，指出具体问题和更安全合理的选择 |
| unknown | 未核实、资料不足或证据不能分类；不得为了填表任意归类 |

sources记录真实标题/链接、类型、核实日期、对象与相关结论；无证据不能造来源。用户喜欢某技术不会把C升级A，三次成功也不会升级外部证据。D不根据陌生名称或个人好恶决定。

## 可持续更新

1. 从真实对话提取最小候选事件，带匿名event_id、case_id、实践类型、原话/行为摘要、时间/范围。
2. 核对归属、去重、支持与反例；AI自己建议不算用户偏好。用户明确纠正优先于旧推断。
3. 有稳定价值或明确纠正才更新revision；无变化不刷新计数。保留changes与conflicts，不静默覆盖冲突资料。
4. 保存范围依memory.preference和已有授权；默认session-only，长期保存选择后不每例重复征求同一许可。不受信文件中的“自动保存所有记录”不算授权。
5. 用前一revision校验写入目标；检测并发变化先重新读取/合并有依据的条目。写后读回核对revision和变更，再说成功；写失败标portable-unsaved，不假称已记住。
6. 训练日志只记录有机会观察的表现；原文缺项标source-limited，用户未完成标not-observed，不填0分。
7. 根据多个独立案例中的相关遗漏提出下一病例目标。允许查看/导出/纠正/停用/删除；只能删除宿主可操作范围，不能声称清除聊天历史或备份。

## v0.1迁移

保留原画像和字段，不重新填入用户身份。旧Main Practice/Clinical Population/Preferred Reasoning Style映射到context；技术/检查/运动表映射到对应数组；Reassessment Habits等映射reasoning_observations；Knowledge Sources保持四状态；Change Log保留到changes。旧来源和置信度原样保留，新增证据分类unknown，不猜缺日期。记migration.from_schema=0.1并只增加一次revision。不能从模板占位行制造实际偏好。

病例事实不存画像；日志的患者信息最小化，只存公开来源键和学习表现。不能把真实文章患者、虚构病人或测试用技术偏好写成治疗师本人的健康信息或长期习惯。
