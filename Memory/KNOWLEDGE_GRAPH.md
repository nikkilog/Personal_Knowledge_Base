# Knowledge Graph

```text
MEMORY_ROLE: LIGHTWEIGHT_RELATION_ROUTER
STATUS: CURRENT
LAST_REVIEWED: 2026-10-25
```

本文件只保存“从哪个实体应路由到哪个 owner”的轻量关系。详细定义看 `ENTITY_MEMORY.md`，详细知识看 `Knowledge/`，项目状态看对应 Project。

## Workspace 结构关系

```text
AI_WORKSPACE --contains--> PROMPT_LIBRARY
Owner: 02_PROMPT_LIBRARY/00_PROMPT_INDEX.md
Evidence: 根目录 `AGENTS.md` §1–§3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> PKB
Owner: Personal_Knowledge_Base/PROJECT.md
Evidence: 根目录 `AGENTS.md` §1–§3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> WORKSPACE_CONTROL
Owner: Workspace_Control/WORKSPACE.md
Evidence: 根目录 `AGENTS.md` §1–§3
Last Confirmed: 2026-08-23

AI_WORKSPACE --contains--> ACCOUNT_BOOTSTRAP
Owner: 01_ACCOUNT_BOOTSTRAP/
Evidence: 根目录 `AGENTS.md` §1
Last Confirmed: 2026-08-23

PKB_MEMORY --derived_from--> PKB_KNOWLEDGE
Owner: Personal_Knowledge_Base/PROJECT.md
Evidence: `Personal_Knowledge_Base/AGENTS.md` §5
Last Confirmed: 2026-08-23

ACCOUNT_BOOTSTRAP --derived_from--> PKB_MEMORY
Owner: 01_ACCOUNT_BOOTSTRAP/
Evidence: 根目录 `AGENTS.md` §1
Last Confirmed: 2026-08-23

WORKSPACE_CONTROL --routes_to--> PROJECTS
Owner: Workspace_Control/PROJECTS.md
Evidence: 根目录 `AGENTS.md` §1–§2
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

```

## 路由规则

- 关系变化先在对应 owner 稳定，再更新本图。
- 项目能力之间的使用与接入状态回到各项目 Current 验证；本图只保留稳定 owner 路由，不从可能关系推断已接入。
- 本图不保存版本、branch、commit、run_id、Current Artifact 或下一步。
