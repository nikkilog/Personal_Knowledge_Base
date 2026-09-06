# Entity Memory

```text
MEMORY_ROLE: STABLE_ENTITY_DICTIONARY
STATUS: CURRENT
LAST_REVIEWED: 2026-08-23
```

本文件只回答“实体是什么、它不是什么、去哪里确认”。Lifecycle、版本、branch、commit、run_id、当前任务和下一步不在这里维护。

## USER

- Canonical Name: `USER`
- Aliases: Nikki、用户
- Type: Person / Operator
- Definition: 以独立站电商为核心的经营者、运营决策者和系统建设者。
- Not This: 不等同于单一站点、单一项目或纯软件工程角色。
- Owner: `Knowledge/PERSONAL_CONTEXT.md`
- Relations: 经营 PBS、NRP、Apollo；建设并使用 AI Workspace。
- Evidence: `Knowledge/PERSONAL_CONTEXT.md` §1–§2
- Last Confirmed: `2026-08-13`

## AI_WORKSPACE

- Canonical Name: `AI_Workspace_Next`
- Aliases: AI Workspace、新 Workspace
- Type: Workspace / Local source-of-truth system
- Definition: 统一承载账号入口、Prompt、PKB、Projects 与 Workspace 治理的本地工作空间。
- Not This: 不是 ChatGPT 账号 Memory，也不是任一 Project 的替代 Current。
- Owner: 根目录 `AGENTS.md`；最终总入口由 `00_START_HERE.md` 持有。
- Relations: contains Prompt Library、PKB、Projects、Workspace Control、Account Bootstrap。
- Evidence: 迁移总合同 §0、§3
- Last Confirmed: `2026-08-23`

## PROMPT_LIBRARY

- Canonical Name: `Prompt Library`
- Aliases: `02_PROMPT_LIBRARY`
- Type: Workspace component / Prompt authority
- Definition: 全部正式 Prompt 的唯一 Current authority。
- Not This: 不是 Prompt 流水线；索引不是运行依赖；Skill 中的 pointer 不是第二份正文。
- Owner: `02_PROMPT_LIBRARY/00_PROMPT_INDEX.md`
- Relations: provides standalone prompts to chats and project workflows。
- Evidence: 迁移总合同 §3.3；`02_PROMPT_LIBRARY/00_PROMPT_INDEX.md`
- Last Confirmed: `2026-08-23`

## ACCOUNT_BOOTSTRAP

- Canonical Name: `Account Bootstrap`
- Aliases: `01_ACCOUNT_BOOTSTRAP`
- Type: Workspace component / Derived account initialization layer
- Definition: 从完成后的 Workspace 与 Memory 提炼两个 GPT 账号共用的初始化材料。
- Not This: 不是第二套知识 Source of Truth，不能反向覆盖 Workspace。
- Owner: `01_ACCOUNT_BOOTSTRAP/`
- Relations: derives from PKB Memory and Knowledge; initializes GPT accounts。
- Evidence: 迁移总合同 §3.2
- Last Confirmed: `2026-08-23`

## PKB

- Canonical Name: `Personal_Knowledge_Base`
- Aliases: PKB、个人知识库
- Type: Repository / Durable personal knowledge system
- Definition: 保存长期个人上下文、协作偏好、可复用知识与已验证通用 Pitfall；Memory 是高频投影，Knowledge 是详细权威。
- Not This: 不是外部项目状态仓库，不保存项目 Current、版本或下一步。
- Owner: `Personal_Knowledge_Base/PROJECT.md`、`AGENTS.md` 与本地 Git。
- Relations: Memory derives from Knowledge; may inform but does not override Projects。
- Evidence: `Personal_Knowledge_Base/PROJECT.md`；迁移总合同 §3.4–§3.5
- Last Confirmed: `2026-08-23`

## WORKSPACE_CONTROL

- Canonical Name: `Workspace_Control`
- Aliases: Workspace Control
- Type: Repository / Workspace governance
- Definition: 管理项目登记、路径、Lifecycle、Profile、Privacy、Current Authority、Closeout Method 和跨项目治理。
- Not This: 不是 Project Current，也不保存项目详细版本、run_id 或下一步。
- Owner: `Workspace_Control/WORKSPACE.md`、`Workspace_Control/PROJECTS.md`
- Relations: governs project registry and Workspace lifecycle; routes to Projects。
- Evidence: 迁移总合同 §3.7；`Workspace_Control/PROJECTS.md`
- Last Confirmed: `2026-08-23`

## PBS

- Canonical Name: `Plumbingsell`
- Aliases: PBS、plumbingsell.com
- Type: Site / Business context
- Definition: 管道、阀门、管件、管材、排水及相关产品的独立站业务。
- Not This: 不等同于 Console Core、CAH 或某个单一 PBS 项目仓库。
- Owner: 详细业务背景在 `Knowledge/PERSONAL_CONTEXT.md`；具体项目事实在各 PBS Project。
- Relations: uses Shopify and Google Ads workflows; consumes some shared Workspace capabilities。
- Evidence: `Knowledge/PERSONAL_CONTEXT.md` §2
- Last Confirmed: `2026-08-13`

## NRP

- Canonical Name: `NRP`
- Aliases: nrpequip.com
- Type: Site / Business context
- Definition: Rubber Track 与 Undercarriage Parts 独立站业务。
- Not This: 不等同于 PBS 或 Apollo。
- Owner: `Knowledge/PERSONAL_CONTEXT.md` §2；具体项目事实由对应 Project 持有。
- Relations: has SKU, compatibility, feed, PDP and search-matching workstreams。
- Evidence: `Knowledge/PERSONAL_CONTEXT.md` §2
- Last Confirmed: `2026-08-13`

## APOLLO

- Canonical Name: `Apollo`
- Aliases: apolloliftus.com、APOLLO
- Type: Site / Business context
- Definition: Pallet Jack、Stacker、Lift Table 及其专用 Spare Parts 的物料搬运设备独立站业务。
- Not This: 专用设备配件不能仅因外形相似而自动当作普通五金；不等同于 PBS 或 NRP。
- Owner: `Knowledge/PERSONAL_CONTEXT.md` §2；具体项目事实由对应 Project 持有。
- Relations: has commerce and Google Ads analysis workstreams。
- Evidence: `Knowledge/PERSONAL_CONTEXT.md` §2
- Last Confirmed: `2026-08-13`

## CAH

- Canonical Name: `Commerce Analytics Hub`
- Aliases: CAH
- Type: Project / Cross-source commerce analytics infrastructure
- Definition: 连接 Shopify、GA4、Search Console、Google Ads、Merchant Center、Meta Ads、AWIN 与 Google Sheets 的 Operator-First 分析与数据基础设施。
- Not This: 不是 Console Core 的别名，也不是所有电商操作系统的总称。
- Owner: `Projects/Commerce_Analytics_Hub/PROJECT.md`
- Relations: integrates commerce and advertising data; produces operator-readable outputs。
- Evidence: `Knowledge/PERSONAL_CONTEXT.md` §2；`Workspace_Control/PROJECTS.md`
- Last Confirmed: `2026-08-23`

## CONSOLE_CORE

- Canonical Name: `Console Core`
- Aliases: CONSOLE_CORE
- Type: Project / Reusable commerce-operations infrastructure
- Definition: 为多个 Shopify 项目提供站点与账号路由、非敏感 Secret 名称、Sheet/Job 注册、Schema、受控写入与运行治理等共享能力。
- Not This: 不等同于 PBS；不等同于 CAH；与 COS 的身份关系未确认，不能自动合并。
- Owner: `Projects/Console_Core/PROJECT.md`
- Relations: may serve PBS and other Shopify projects; may use Workspace Secret Resolver。
- Evidence: `Projects/Console_Core/PROJECT.md` §Project Purpose、§Open Questions
- Last Confirmed: `2026-08-23`

## WORKSPACE_SECRET_RESOLVER

- Canonical Name: `Workspace Secret Resolver`
- Aliases: WORKSPACE_SECRET_RESOLVER
- Type: Project / Shared secret-resolution contract
- Definition: 提供版本化、可测试、project-aware 的 Secret 读取逻辑与非敏感命名规则，不集中保存 Secret 值。
- Not This: 不是 Secret 值仓库，不生成或轮换 Secret，不替代认证协议，不自动修改下游项目。
- Owner: `Projects/Workspace_Secret_Resolver/PROJECT.md`
- Relations: can be adopted by independent Workspace projects; physical Secret values remain outside source control。
- Evidence: `Projects/Workspace_Secret_Resolver/PROJECT.md` §Purpose、§Authority boundaries
- Last Confirmed: `2026-08-23`

## 维护规则

- 新增或修改实体时，必须保留 Canonical Name、Aliases、Type、Definition、Not This、Owner、Relations、Evidence、Last Confirmed。
- 任何动态状态回到实体 owner，不在本文件复制。
