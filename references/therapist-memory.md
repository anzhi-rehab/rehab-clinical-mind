# Therapist Memory / Memory Adapter

## 数据边界

公开 Skill 只有规则和空模板。各治疗师使用独立私人画像，病例摘要、学习日志也放在私人位置，不写回安装目录或公开 Git 仓库。路径由宿主或用户指定；无可信私人位置时输出可保存文本，不猜测远程写入位置。

V0.1 不自建记忆库，不在后台训练模型。`rehab-clinical-mind / therapist-local-alias` 只是逻辑命名空间，不意味着平台已实现隔离。共享账号、多人会话或归属冲突时确认当前画像属于谁，只需非实名别名，不合并其他人的习惯。

## Adapter 决策

| 实际宿主能力 | 执行 |
| --- | --- |
| 可隔离、可读写的持久记忆或私人文件 | 读当前画像，在已有授权范围保存最小更新，看实际结果后再说已保存 |
| 只有不透明对话记忆，无法保证字段读回 | 可作辅助，以可导出 THERAPIST_PROFILE.md 为主，不承诺独立记忆库 |
| 无持久记忆、只读、写入失败 | 会话内使用，输出完整更新稿或文件，说明跨会话需保存并重传 |

首次简短说明默认会话内使用，询问/沿用长期画像选择；不重复请求已有授权。病例长期保存须明确选择该去标识摘要或已选择此类自动摘要；无授权仅输出草稿。拒绝记忆不影响四种模式。

## Therapist Model 字段

按 `templates/THERAPIST_PROFILE.md` 的稳定英文键名记录，内容可用任意语言。空值填 unknown。包含 Main Practice、Clinical Population、Preferred Techniques、Preferred Assessments、Preferred Reasoning Style、Frequently Used Exercises、Reassessment Habits、Clinical Strengths、Knowledge Sources、Current Learning Topics、Development Areas、Possible Reasoning Biases、Technique Preference Confidence、Last Updated。附非实名 Profile ID、Schema Version、Profile Revision、Memory Status。

长期推断保留范围、来源（自述/观察）、无身份的会话或 episode 别名、支持次数、反例、最近核对时间。偏好不等于能力认证或技术优效证据。

无技术偏好依据时，Preference Status 写 not-established，技术表保留空表；不建立虚假的 unknown 技术行。已有条目的 Confidence 只用 low / medium / high，不能混入 unknown 或叙述句。学习兴趣放 Current Learning Topics，尚未认可/应用的资料放 Knowledge Sources。

## 偏好置信度（工作约定，非统计概率）

| 级别 | 最少依据 |
| --- | --- |
| low | 单次提及/使用或一次自述，只是候选习惯，不称流派归属 |
| medium | 至少两个独立讨论/病例重复出现且情境和理由一致，或明确长期自述经后续实际讨论支持 |
| high | 至少三个独立、跨时间的实际病例/讨论支持，并由治疗师确认稳定偏好；仍限相应人群与情境 |

同一病例多轮、重复上传、AI 自己建议不算多次使用。模拟练习标 educational，不计真实应用次数。阈值用于防止过快贴标签，不是效能研究。用户明确「已不是我的偏好」立即纠正当前排序，保留必要修订痕迹，不要求凑反例。无日期/纵向资料不认定长期稳定。

## 更新、冲突与撤回

只更新稳定、有未来价值的信息或明确纠正。提取候选 → 核对归属/隐私 → 比较旧画像 → 去重 → 标明自述/观察和置信度 → 简短变更摘要 → 授权位置写入并核验。无新信息不变 revision。

当前明确纠正优先于旧推断；两个画像冲突、归属不明或时间不可比时不静默覆盖，保留冲突字段，问一项关键澄清。升级 schema 保留旧字段，新字段 unknown，不因版本更高覆盖全部资料。

支持查看、导出、纠正、停止记忆、删除某项/清空。删除只作用于有权限的记忆/文件，报告实际范围，不声称删除平台聊天历史或备份。公开模板不填入当前使用者资料。

## 反偏科与成长

多个有充分记录的独立病例反复略过相关方向时，先问「是未记录，还是确实未评估？」。区分稳定习惯与可能偏差。样本不足只提出当前病例替代假设，不贴能力标签。

适度问「暂时不从最常用的方向解释，还有什么可能？」。提示以当次决策价值为依据，同次复盘不重复。成长输出用到哪些记录、样本限制、一个学习任务和下次复盘指标。
