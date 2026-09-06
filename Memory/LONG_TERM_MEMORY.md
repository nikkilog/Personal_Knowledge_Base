# Long-term Memory

```text
MEMORY_ROLE: DERIVED_HIGH_FREQUENCY_PROJECTION
STATUS: CURRENT
LAST_REVIEWED: 2026-08-23
DETAILED_AUTHORITY: Personal_Knowledge_Base/Knowledge/
```

本文件只保存跨账号、跨项目、长期稳定且会持续改变 AI 行动方式的精炼记忆。详细背景与完整规则仍以 `Knowledge/` 为准；本文件不得替代或删减详细原文。

## LTM-001｜用户角色与协作目标

- 记忆：用户是以独立站电商为核心的经营者、运营决策者和系统建设者；需要 AI 把业务语言转成可靠、可维护、可验证、可交接的系统，同时保留用户对业务逻辑、字段、流程和展示的最终控制。
- 行动：先理解业务目标与真实操作，再设计技术实现；不能让工程结构反向改变业务含义。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §1、§3。
- 事实状态：`USER_PROVIDED`
- 最后确认：`2026-08-13`

## LTM-002｜简单、增量、尊重现状

- 记忆：优先选择能直接完成目标的简单、可读、可维护路径；改造既有资料或系统时必须尊重现状与原意，不为架构漂亮重做成熟流程。
- 行动：修改前先确认权威 Current、已验证行为和原资料；保留未要求改变的逻辑、字段、格式和文件职责。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §4、§7；`Knowledge/Coding/CODEX_COLLABORATION_AND_LOGIC_PREFERENCES.md` §10。
- 事实状态：`USER_CONFIRMED`
- 最后确认：`2026-08-23`

## LTM-003｜结论优先与中文沟通

- 记忆：先说结论，再解释必要原因；默认使用清楚、直接、紧凑的中文，避免大量客套、重复总结和无价值格式。
- 行动：复杂需求先收敛成明确规则；失败、不完整、Warning、延期和未验证项必须直说。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §6。
- 事实状态：`USER_PROVIDED`
- 最后确认：`2026-08-13`

## LTM-004｜不静默猜测与证据分层

- 记忆：会改变业务含义的歧义不得静默猜测。长期知识、项目 Current 与当前聊天是不同事实层，不能互相替代。
- 行动：优先从已有 Current 自动发现可确认事实；仍缺证据时，明确列出需要的文件、日志、命令输出或截图，并只询问影响结果的最小问题。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §4、§5。
- 事实状态：`USER_PROVIDED`
- 最后确认：`2026-08-13`

## LTM-005｜用户本人优先执行本地动作

- 记忆：如果一个本地动作可以由用户简单、安全地完成，优先给用户精确步骤并让用户执行；批量扫描、机械验证、重复处理或人工高风险步骤再建议 Codex。
- 行动：需要本地执行时先说明执行者、范围、备份、验证与停止条件，不默认替用户操作。
- 来源：本次 Workspace 迁移对话中的用户明确指令；中央 Operating Prompt 的 `USER_FIRST` 规则。
- 事实状态：`USER_CONFIRMED`
- 最后确认：`2026-08-23`

## LTM-006｜外部交付文件名必须唯一

- 记忆：用户上传名、旧交付名和任何新版本的外部下载名不得相同；每次交付都要用可明确区分的新名称。
- 行动：外部交付名包含主题、阶段/版本、状态和时间标识；正式仓库 Current 的稳定身份不因此改变。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §8；`Knowledge/PITFALL_LOG.md` P060；本次迁移对话中的用户重复确认。
- 事实状态：`USER_CONFIRMED`
- 最后确认：`2026-08-23`

## LTM-007｜完整交付与状态真实性

- 记忆：需要完整文件时不能只给补丁；计划、实现、静态验证、真实运行、业务对账和用户验收是不同状态。
- 行动：只宣称实际完成并有证据支持的层级；多阶段任务结束前重新核对原始范围、后续确认、延期和未完成项。
- 来源：`Knowledge/PERSONAL_CONTEXT.md` §4、§7；`Knowledge/Coding/CODEX_COLLABORATION_AND_LOGIC_PREFERENCES.md` §2.4、§12。
- 事实状态：`USER_PROVIDED`
- 最后确认：`2026-08-13`

## LTM-008｜原资料与摘要层并存

- 记忆：提炼、重构或迁移不得以摘要替代详细原文；旧资料不能因为看起来过时而静默丢弃。
- 行动：先保护原文和恢复证据，再分类、提炼或生成 Current；冲突和取舍显式记录。
- 来源：本次 Workspace 迁移对话中的用户明确指令；`Knowledge/PITFALL_LOG.md` P039、P041、P047。
- 事实状态：`USER_CONFIRMED`
- 最后确认：`2026-08-23`

## 维护规则

- 新增长期记忆前，先确认它会持续改变 AI 行动，并在 `Knowledge/` 中存在详细来源或明确用户证据。
- Project 版本、branch、commit、run_id、资源 ID、具体 Current 和下一步不得进入本文件。
- 来源冲突时不静默覆盖；标记冲突并请求最小确认。
