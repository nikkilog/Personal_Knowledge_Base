# Knowledge Graph

```text
MEMORY_ROLE: LIGHTWEIGHT_RELATION_ROUTER
STATUS: CURRENT
LAST_REVIEWED: 2026-08-23
```

本文件只保存“从哪个实体应路由到哪个 owner”的轻量关系。详细定义看 `ENTITY_MEMORY.md`，详细知识看 `Knowledge/`，项目状态看对应 Project。

## Workspace 结构关系

```text
AI_WORKSPACE --contains--> PROMPT_LIBRARY
Owner: 02_PROMPT_LIBRARY/00_PROMPT_INDEX.md
Evidence: 迁移总合同 §3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> PKB
Owner: Personal_Knowledge_Base/PROJECT.md
Evidence: 迁移总合同 §3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> WORKSPACE_CONTROL
Owner: Workspace_Control/WORKSPACE.md
Evidence: 迁移总合同 §3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> ACCOUNT_BOOTSTRAP
Owner: 01_ACCOUNT_BOOTSTRAP/
Evidence: 迁移总合同 §3.2
Last Confirmed: 2026-08-23

PKB_MEMORY --derived_from--> PKB_KNOWLEDGE
Owner: Personal_Knowledge_Base/PROJECT.md
Evidence: 迁移总合同 §3.4–§3.5
Last Confirmed: 2026-08-23

ACCOUNT_BOOTSTRAP --derived_from--> PKB_MEMORY
Owner: 01_ACCOUNT_BOOTSTRAP/
Evidence: 迁移总合同 §3.2
Last Confirmed: 2026-08-23

WORKSPACE_CONTROL --routes_to--> PROJECTS
Owner: Workspace_Control/PROJECTS.md
Evidence: 迁移总合同 §3.7
Last Confirmed: 2026-08-23
```

## 业务与能力关系

```text
USER --operates--> PBS
Owner: Knowledge/PERSONAL_CONTEXT.md
Evidence: Knowledge/PERSONAL_CONTEXT.md §1–§2
Last Confirmed: 2026-08-13

USER --operates--> NRP
Owner: Knowledge/PERSONAL_CONTEXT.md
Evidence: Knowledge/PERSONAL_CONTEXT.md §1–§2
Last Confirmed: 2026-08-13

USER --operates--> APOLLO
Owner: Knowledge/PERSONAL_CONTEXT.md
Evidence: Knowledge/PERSONAL_CONTEXT.md §1–§2
Last Confirmed: 2026-08-13

CAH --integrates_data_from--> COMMERCE_AND_AD_PLATFORMS
Owner: Projects/Commerce_Analytics_Hub/PROJECT.md
Evidence: Knowledge/PERSONAL_CONTEXT.md §2
Last Confirmed: 2026-08-13

PBS --consumes_capability_from--> CONSOLE_CORE
Owner: Projects/Console_Core/PROJECT.md
Evidence: Projects/Console_Core/PROJECT.md §Project Purpose
Last Confirmed: 2026-08-23

CONSOLE_CORE --may_use--> WORKSPACE_SECRET_RESOLVER
Owner: respective Project Current
Evidence: Projects/Console_Core/PROJECT.md; Projects/Workspace_Secret_Resolver/PROJECT.md
Last Confirmed: 2026-08-23
```

## 路由规则

- 关系变化先在对应 owner 稳定，再更新本图。
- `may_use` 不代表已完成接入；实际接入状态必须回到项目 Current 验证。
- 本图不保存版本、branch、commit、run_id、Current Artifact 或下一步。
