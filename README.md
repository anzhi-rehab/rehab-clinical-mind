# Rehab Clinical Mind

**v0.2.0 · Real Case Guided Reasoning · 真实病例引导式临床推理训练**

使用真实、可追溯的康复病例，让治疗师自己问病史、建假设、选检查、更新判断、设计干预和复测，最后才对照作者方案与循证资料。AI担当带教伙伴，适应个人技术体系，也指出确认偏倚和风险。

## 直接开始

```text
使用 Rehab Clinical Mind，进入 Real Case Guided Reasoning。
今天按2道肌骨/脊柱/运动康复 + 2道脑卒中康复安排，一次只给一道。
先检索并锁定可追溯的真实病例。首轮只给基本资料、主诉和病程。
我决定问什么、查什么；原文未报告就明确未知，不编造结果。
等我说“我做完了”再完整复盘。目前只在会话内使用学习画像。
```

每日模式是随用户启动的队列，本项目没有后台定时器。搜不到合格病例就报告缺额，不能用模拟凑数。没有来源访问能力时，可读取此前核实的完整病例包；只有模型记忆不能开真实病例。

## 五种模式

| 模式 | 用途 |
| --- | --- |
| Real Case Guided Reasoning | 真实来源病例，用户主导提问，固定患者数据，不提前揭答案 |
| Guided Reasoning | 用户提供病例的渐进推理；每轮最多1～3个问题/检查 |
| Teaching Analysis | 完整教学、评估逻辑、条件化方案和复测 |
| Case Review | 已实施病例复盘，分开观察与因果解释 |
| Professional Growth | 技术偏好、学习教材、推理习惯、薄弱点与成长计划 |

真实病例模式不会继承旧引导模式的主动假设菜单。只有明确整例结束/答案/评价要求才进入七部分Debrief；局部检查评价不算结束。

## 真实性规则

- 一例一锁：文章版本、PMID/PMCID/DOI或稳定原始URL、患者编号、事实定位、时间点。
- 【病例事实】【原作者解释】【使用者假设】【AI临床点评】分开。
- 未报告、未访问、含糊、冲突分开；不能编ROM/MMT/影像/量表/反应。
- 新干预无原文复测结果，就只能讨论设计，不能模拟“减痛几分”。
- 默认首轮不露诊断性标题；用户要来源时提供，复盘给完整核实引文。宿主检索界面可能显示标题，不能承诺绝对盲法。
- 原文作者不自动正确：病例证据、因果归因、自然恢复、过度保护、功能能力和现代证据都需要审阅。

病例来源顺序为PubMed/PMC、专业康复期刊与可追溯Physiopedia病例；Physiotutors主要辅助复盘，Simucase主要参考虚拟流程。完整资格规则见[source-policy](references/source-policy.md)。

## 临床学习重点

症状行为→假设→高信息价值检查→概率更新→功能问题→干预→复测→进阶。单个阳性试验不能确诊；某肌肉弱不能推出一整条必然疼痛因果链。

肌骨训练连接负荷、24h反应、可重复任务、长期能力与专项回归；卒中训练连接医疗稳定、移动/上肢任务、重复剂量、家庭环境和参与。短时减痛或肌张力变化不等于恢复完整功能。安全和患者目标先于技术偏好。

## 个人画像与隐私

保留常用检查、技术、强项、易漏点、负荷/功能/复测习惯、鉴别和风险筛查观察。技术具体主张可记A充分支持、B证据有限、C个人经验、D冲突/风险，无法核实为unknown；这不是GRADE，也不是给流派打分。

长期成长依赖宿主实际保存并读回私人画像，本项目没有独立数据库或模型训练。支持JSON及旧Markdown迁移、事件去重、反例、撤回、纠正、导出。一次练习不计真实临床应用；同一病例多轮不计多个独立支持。公开项目仅空模板，填写后的资料应放在与安装目录分开的私人位置，不能提交到本仓库。

## 项目结构与完整文件

入口与每个核心文件均可直接打开；保留原项目有用的示例、测试和MIT许可。

| 路径 | 内容 |
| --- | --- |
| [SKILL.md](SKILL.md) | 总规则、五模式路由、按需读取 |
| [references/source-policy.md](references/source-policy.md) | 独立真实病例来源政策 |
| [references/no-fabrication.md](references/no-fabrication.md) | 数据契约、缺失状态、纠错 |
| [references/safety-core.md](references/safety-core.md) | 风险优先与转介边界 |
| [references/reasoning-framework.md](references/reasoning-framework.md) | 概率、功能、负荷和Test–Retest |
| [references/interaction-modes.md](references/interaction-modes.md) | 保留四模式及真实模式优先关系 |
| [references/evidence-policy.md](references/evidence-policy.md) | 证据、教材及病例事实分离 |
| [references/therapist-memory.md](references/therapist-memory.md) | 私人记忆适配及偏好置信度 |
| [references/profile-data.md](references/profile-data.md) | 画像字段、A/B/C/D、更新和v0.1迁移 |
| [references/case-learning.md](references/case-learning.md) | 已实施病例学习与泛化边界 |
| [workflows/real-case-guided.md](workflows/real-case-guided.md) | 来源锁→逐项回应→安全/结束门 |
| [workflows/debrief.md](workflows/debrief.md) | 七部分复盘 |
| [workflows/daily-practice.md](workflows/daily-practice.md) | 每日2+2轮换、去重、难度和缺额 |
| [templates/CASE_LOCK.md](templates/CASE_LOCK.md) | 来源、患者、事实账本、揭示状态 |
| [templates/MSK_CASE.md](templates/MSK_CASE.md) | 肌骨/脊柱/运动康复模板 |
| [templates/STROKE_CASE.md](templates/STROKE_CASE.md) | 卒中评估、量表、任务剂量模板 |
| [templates/PERSONAL_PROFILE.json](templates/PERSONAL_PROFILE.json) | 空白结构化个人画像 |
| [templates/TRAINING_LOG.json](templates/TRAINING_LOG.json) | 空白单病例训练日志 |
| [templates/THERAPIST_PROFILE.md](templates/THERAPIST_PROFILE.md) | 兼容旧版Markdown画像 |
| [templates/CASE_MEMORY.md](templates/CASE_MEMORY.md) | 去标识临床复盘模板 |
| [templates/LEARNING_LOG.md](templates/LEARNING_LOG.md) | 教材/知识来源学习模板 |
| examples/ | 保留四个明确虚构的旧模式示例，不当真实病例库 |
| [tests/real-case-scenarios.md](tests/real-case-scenarios.md) | v0.2行为场景及观察标准 |
| [tests/benchmark-cases.md](tests/benchmark-cases.md) | 原20项基准 |
| [tests/v0.2-results.md](tests/v0.2-results.md) | 本次实际验证范围与输出记录 |
| [tests/test-results.md](tests/test-results.md) | 原版本测试记录，仅代表当时覆盖 |
| agents/openai.yaml、assets/icon.svg | 可选OpenAI界面元数据与图标 |
| LICENSE、CHANGELOG.md、.gitignore | MIT许可、版本变化、辅助隐私排除 |

## 兼容与加载

核心是带YAML frontmatter的SKILL.md及相对路径Markdown/JSON文件，不依赖某个专有API。使用支持目录型Agent Skill的宿主，完整导入整个目录；若需本地目录名，使用rehab-clinical-mind。不能只读入口而漏掉引用政策。

ChatGPT、Claude、Codex等产品的实际导入入口、搜索和持久保存能力随环境而异；本版不承诺任意GitHub URL一键安装或已在全部平台实测。没有技能导入功能时可以将完整规则作为当前会话资料读取，但这不等于持久安装。用户私人画像不要放进技能源码。

## 验证与贡献

新工作流有行为场景，格式验证只检查包装；实际已执行范围记录于tests。规则依赖模型遵守，不能保证零幻觉，不作为自主诊断、分诊或处置系统。移植后应复查缺失值、患者锁、时间点、揭示门、安全和记忆隔离。

贡献请提供虚构复现、实际/预期行为和宿主版本；不要上传可识别患者资料或版权全文。第三方链接内容不适用本项目MIT授权。
