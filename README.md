# Rehab Clinical Mind

A personalized clinical reasoning skill for rehabilitation professionals.

面向康复治疗师的临床推理与反思伙伴。通过长期读取个人画像，它可以逐渐适应不同治疗师的评估习惯、技术偏好和表达方式，同时保留安全筛查、竞争假设和复测。

**它不是诊断机器人。** 用于 educational use 和 support clinical reasoning，does not replace professional judgment。不根据单一体征确定疾病，不替代医学评估，不授予任何执业权限。V0.1 为指令型 Skill，需要支持相应文件读取的 AI 宿主；没有后端、数据库、API、账号系统或模型微调。

## 能帮你做什么

- 训练临床推理，建立和更新竞争假设。
- 选择当前有信息价值的评估，避免堆检查。
- 分析功能、动作、负荷和生活背景，讨论条件化运动方案。
- 病例复盘，分清观察、假设、即时反应与随访结果。
- 从个人经验中学习，逐渐调整合理方案排序与表达。
- 发现知识缺口和可能遗漏，同时保留风险筛查。

## 四种模式

| 模式 | 适合什么时候 | 可以这样说 |
| --- | --- | --- |
| Guided Reasoning（默认） | 想自己练思考，每轮只推进少量信息 | 用引导模式带我分析，每次最多三个问题或检查，等我给结果。 |
| Teaching Analysis | 想看一个病例的完整教学解析 | 解释支持和反对依据、下一步评估目的、干预分支和复测。 |
| Case Review | 已经实施干预，想认真复盘 | 帮我看哪些结果支持原假设，哪些不能证明，并生成经验草稿。 |
| Professional Growth | 想分析自己的习惯或补知识 | 根据可见记录，帮我找可能忽略的方向；我想补跑步负荷管理。 |

引导模式不会先抛出最终技术答案。教学模式输出的是**可审计的临床依据**，不宣称展示模型隐藏思维链。任何模式出现重要风险都先升级评估。

## 三分钟开始

安装后选择 Rehab Clinical Mind，发送：

```text
请用 Rehab Clinical Mind 的 Guided Reasoning 模式。
我主要做成人肌骨康复，常用的技术暂时只作背景，不要据此贴流派标签。
目前只在会话内使用画像。
下面是去标识或虚构病例：
患者目标：……
症状行为与负荷史：……
风险信息：哪些已询问并否认，哪些阳性，哪些还未问：……
已做检查及结果：……
我现在的假设：……
请只推进下一步，并等待我的结果。
```

不要把真实患者身份放进提示词。首次没有画像也能用，不必先填完问卷。

## 个体化如何发生

治疗师偏好只重新排序**安全、适用且合理**的选项。患者目标、意愿、禁忌证、证据与专业范围先于治疗师喜好。DNS、PIR、MET、PNF、悬吊、力量训练、疼痛科学、负荷管理和神经动力学都不是默认正确答案。

[THERAPIST_PROFILE.md](templates/THERAPIST_PROFILE.md) 记录工作方向、人群、常用技术/评估/运动、推理风格、复测习惯、强项、知识来源、学习主题、发展方向和可能偏差。

- low：一次自述或观察，候选习惯。
- medium：至少两个独立讨论/病例支持，情境与理由一致。
- high：至少三个跨时间的独立支持，并由治疗师确认稳定偏好。

这是工作约定，不是统计概率或能力认证。重复聊天不重复计数，模拟案例不计真实应用；没有偏好就保持空表。纠正、撤回与停止记忆随时可提出。

如果长期记录显示总从某块肌肉出发，Skill 会先核对其他方向究竟是没记录还是没评估，再适度提出替代假设。低频检查不自动等于缺陷，也不要求每个病例都唱反调。

## 记忆与迁移

**长期成长依赖宿主实际保存并重新读取资料，不是安装后自动拥有独立数据库。**

| 环境 | 用法 |
| --- | --- |
| 可按用户隔离的持久记忆/私人文件 | 读取当前画像，在已有授权内保存稳定且有价值的更新，报告真实保存结果 |
| 只有不透明对话记忆 | 辅助使用，以可导出的画像文件为主 |
| 无持久记忆或写入失败 | 输出完整画像文本，保存为 THERAPIST_PROFILE.md，下次或换平台后重新上传 |

每位治疗师保有独立私人副本。不要把实际画像写进安装目录或公开仓库；仓库只保留空模板。可以说「导出画像」「纠正我的 PIR 偏好」「停止记忆」。删除操作受宿主权限限制，Skill 不能保证删除平台聊天历史或备份。

## 教材、课程与笔记

上传材料先进入 Available Knowledge，并记录实际读取范围。认可某个观点才进入 Accepted Knowledge，报告实际应用才进入 Applied Knowledge，重复使用并确认后才形成 Preferred Knowledge。四种状态互相独立：尝试过不一定认可，认可不一定用过。

Skill 提取概念、评估/干预逻辑、适用情境、局限和互补关系；分开外部证据、教材观点、专家观点、个人经验与模型假设。上传一本书不意味着认可全书；一次成功不升级为医学事实。记录使用 [LEARNING_LOG.md](templates/LEARNING_LOG.md) 和 [CASE_MEMORY.md](templates/CASE_MEMORY.md)。

## 安装与兼容性

官方文档核对：**2026-09-08**。入口受产品、账号、地区和管理员设置影响。以下区分格式兼容与实际宿主验证；本版没有声称完成所有平台端到端导入测试。

本包遵循 [Agent Skills 官方规范](https://agentskills.io/specification)：目录名 `rehab-clinical-mind`，入口含 `name` / `description` YAML frontmatter，规则按需读取。安装 ZIP 应只有一个顶层 `rehab-clinical-mind/` 文件夹，其下直接是 SKILL.md；不要只上传入口遗漏 references/templates。

### ChatGPT

[OpenAI Academy 的 Skills 说明](https://academy.openai.com/public/clubs/work-users-ynjqu/resources/skills) 支持把外部编写的 Skill 上传后审阅安装；[官方 Build skills](https://learn.chatgpt.com/docs/build-skills) 说明技能调用与不同产品入口。当前没有核实本仓库链接可对所有账号一键安装。

推荐：下载发行 ZIP → 在有 Skills/创建技能能力的 ChatGPT 环境上传 → 请求「将上传包作为 Rehab Clinical Mind 安装，保留全部引用文件」→ 按界面完成安装。若当前入口不接受 ZIP，先解压并上传整个技能所需文件；安装后通过 `@` 选择技能。找不到 Skills 能力时，不把普通附件读取称为安装。

降级用法：解压后上传 SKILL.md、六个 references 和三个 templates，明确要求模型读取这些规则；这是当前会话加载，不能承诺自动触发或跨会话记忆。公共商店分发可能需另行打包插件和平台审核，V0.1 不包含插件商店发布。

### Coze / 扣子

按[扣子官方「开发技能」](https://docs.coze.cn/guides_vibe_coding_skill)：在**扣子编程**首页选择「技能」页签，点「上传技能包」，上传 `.zip` 或 `.skill`；平台会解析、安全检测并重新打包，之后按界面完成部署/使用。本项目直接提供 ZIP，不要求自行改后缀。

该入口不等于所有旧版扣子 Agent 的工作流导入；国际 Coze 和不同账号是否开放同一入口未实测。没有核实任意 GitHub URL 一键导入能力。平台重打包后，检查 Safety Core、模式路由和模板仍可读，并重跑安全/记忆烟测。

### 其他 Agent Skills 宿主 / Codex CLI

使用宿主自己的安装目录和权限。对于[官方文档列出的 Codex CLI 本地技能路径](https://learn.chatgpt.com/docs/build-skills)，可把解压后的整个文件夹放入 `~/.agents/skills/rehab-clinical-mind/`（个人）或项目 `.agents/skills/rehab-clinical-mind/`。通过 `/skills` 或 `$rehab-clinical-mind` 调用。托管 ChatGPT 的安装流程不要照搬本地目录命令。

其他宿主按各自文档导入，不能假设所有产品扫描同一路径。`agents/openai.yaml` 是可选 UI 元数据，核心工作流不依赖它。宿主须能读 Markdown 引用文件；基础推理和画像导出不需要联网，时效性临床证据核对需要可用搜索能力。每次新安装先用虚构案例检查表现。

## 隐私与使用边界

不要上传可识别患者身份的信息：姓名、联系方式、证件/病历号、人脸、精确地址/日期、单位和可识别组合。去标识仍可能不充分，优先虚构练习和最小必要摘要。不要将教材全文、实际病例、已填写画像或私人链接提交 GitHub、issue 或公开演示。

本项目不收集或遥测数据，但宿主的存储、权限、数据政策仍适用。安全规则是模型指令，不能保证零遗漏；不作为自动分诊或自主处置系统。红旗示例及依据见 [safety-core.md](references/safety-core.md)。

## 项目文件

| 路径 | 内容 |
| --- | --- |
| SKILL.md | 精炼总调度器 |
| references/safety-core.md | 风险门与转介边界 |
| references/reasoning-framework.md | 假设、评估、干预、复测 |
| references/therapist-memory.md | 画像、置信度、记忆适配 |
| references/case-learning.md | 病例经验与泛化限制 |
| references/interaction-modes.md | 四种模式详细行为 |
| references/evidence-policy.md | 来源、教材和证据分离 |
| templates/ | 画像、病例摘要、学习日志空模板 |
| examples/ | 引导、教学、复盘、红旗四个虚构示例 |
| tests/benchmark-cases.md | 20 项行为基准及通过标准 |
| tests/test-results.md | 实际测试回合、修订与限制 |
| agents/openai.yaml | 可选 OpenAI 界面元数据 |
| .gitignore | 防止常见私人记忆文件误入版本控制的辅助规则 |
| LICENSE / CHANGELOG.md | MIT 许可与版本记录 |

## 测试与贡献

看 [20 项基准](tests/benchmark-cases.md) 与[本版测试记录](tests/test-results.md)。格式检查、六个虚构会话模拟及修订回测不等于临床验证；未经运行的基准不得标通过。跨平台导入后至少运行 B05、B07、B09、B12、B16。

欢迎提交原创规则、虚构复现案例和文档改进。报告问题时提供技能版本、宿主、模式、去标识输入、实际/期望行为；不要提交患者资料或版权教材。修改安全门或记忆规则时，重跑相关基准，附实际输出而非只写「已测试」。

## 发布到 GitHub（维护者）

若得到的是 ZIP 而仓库尚未发布，最少三步：

1. 在 GitHub 新建 Public 仓库 `rehab-clinical-mind`，默认分支 main，不自动添加 README 或 LICENSE。
2. **解压 ZIP 后上传文件夹内全部源码**，使 SKILL.md 在仓库根目录；GitHub 上传 ZIP 不会自动解压。首次提交信息：`Initial release of Rehab Clinical Mind v0.1.0`。若上传界面隐藏 .gitignore，可使用本地 Git 上传全部文件。
3. 在 Releases 创建 `v0.1.0` tag，目标 main，标题 `Rehab Clinical Mind v0.1.0`，粘贴下方说明，附上发行 ZIP 后发布。

这些步骤依据 [GitHub 创建仓库](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)及[管理 Release](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository)官方文档。版本文件和本地 tag 不代表 GitHub Release 已创建。

Release Notes：

```text
- personalized therapist profile
- four clinical reasoning modes
- safety-first framework
- case learning
- portable memory profile
- evidence separation
- initial benchmark tests

Educational workflow v0.1.0. See tests/test-results.md for the scope and limitations of validation.
```

## 长期愿景

同一原始 Skill 可以逐渐适应 DNS + motor control、PIR + MET + active exercise、strength training + load management 或 sling + neuromuscular control 等不同风格。共同保留 Safety Core、clinical reasoning、competing hypotheses、reassessment、evidence awareness 和 scope awareness。

目标是帮助不同康复治疗师成长为更完整、更善于反思、更有自己技术特点的临床工作者，而不是制造统一的「正确治疗师」。

## License

[MIT License](LICENSE)。仓库仅包含原创工作流、规则、模板与虚构案例；第三方链接内容和用户私人教材不因本项目 MIT 许可而获得再分发授权。
