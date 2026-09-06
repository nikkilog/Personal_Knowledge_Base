# Personal Knowledge Base

> 状态：Current
> 最后复核：2026-08-23

## 1. 仓库目的

本仓库用于保存长期稳定、能够跨对话和跨项目复用的个人工作上下文与经验，并用 Memory / Knowledge 分层同时保证高频使用效率和详细信息完整性。

它帮助新的 AI、协作者或未来的自己，在不依赖历史聊天记录的情况下，理解：

* 用户长期从事的业务和工作范围；
* 用户偏好的思考、沟通和交付方式；
* 跨项目适用的操作习惯；
* 已真实发生、值得防止复发的通用 Pitfall；
* 本知识库自身的维护边界。

本仓库不是外部项目的状态仓库，不保存外部项目的当前进度、版本、资源标识、运行记录或下一步。

本地仓库与本地 Git 是 PKB 的编辑和版本权威；GitHub `main` 仅作为供在线 ChatGPT 按需检索的只读镜像。所有内容先在本地修改、验证并提交，再按授权同步镜像。

## 2. Current 资产

### `AGENTS.md`

Personal_Knowledge_Base 仓库的强制操作规则。

负责定义：

* 存储、隐私和访问边界；
* 文件职责；
* 编辑、验证和 Git 规则；
* 项目收口后的知识吸收边界；
* 需要明确授权的操作。

### `PROJECT.md`

本仓库的目的、Current 资产地图和维护入口。

只在仓库职责、正式文件结构、Current 资产或维护方式发生变化时更新。

### `Memory/`

四个精炼、可追溯的高频入口：

* `LONG_TERM_MEMORY.md`：长期稳定且会改变 AI 行动方式的记忆；
* `SHORT_TERM_MEMORY.md`：带复查和到期条件的跨项目近期意识；
* `ENTITY_MEMORY.md`：实体定义、边界、owner 和证据；
* `KNOWLEDGE_GRAPH.md`：实体之间的轻量关系与查找路由。

Memory 是派生层，不替代 `Knowledge/` 的详细原文，也不保存 Project Current。

### `Knowledge/PERSONAL_CONTEXT.md`

长期稳定的个人背景、工作偏好和默认协作方式。

用于帮助 AI 在 AGENTS.md 允许的范围内选择更合适的方案，但不构成删除、提交、发布或其他高影响操作的授权。

### `Knowledge/PITFALL_LOG.md`

已经真实发生、根因足够明确、可跨任务复用且具备验证方式的故障与修复经验。

Pitfall 编号长期稳定；条目合并、迁移或废弃时不得重新编号或复用旧编号。

### `Knowledge/Coding/CODEX_COLLABORATION_AND_LOGIC_PREFERENCES.md`

从原 `AI使用` 完整保留的详细协作与逻辑偏好；需要时查阅，不要求每次对话全文加载。

### `90_Archive/`

保存迁移来源和历史版本原文。Archive 不是 Current；只有在追溯、冲突审查或恢复时读取。

## 3. 文件配合顺序

普通外部项目任务需要个人长期知识时，先按任务语义检索相关条目，只读取命中的文件和必要段落；内容不足时再扩大范围，不为形式完整而通读全部 PKB Current 文件。

解释 PKB 治理、维护 PKB 或执行知识吸收时，按以下顺序使用：

1. 读取 `AGENTS.md`，确定仓库边界和强制规则；
2. 读取 `PROJECT.md`，确认当前正式资产、镜像边界和文件职责；
3. 按任务需要读取相关 `Memory/` 投影；
4. 需要详细背景或规则时读取 `Knowledge/PERSONAL_CONTEXT.md` 或 `Knowledge/Coding/`；
5. 按任务涉及的问题类型查阅 `Knowledge/PITFALL_LOG.md`。

各文件应保持唯一职责。相同知识不得在多个文件中重复保存完整正文；需要关联时优先使用稳定条目名称或 Pitfall 编号引用。

## 4. 在线读取与事实来源

在线 ChatGPT 通过 GitHub 镜像读取 PKB 时，使用以下三层事实结构：

1. **PKB**：长期偏好、治理原则、跨项目协作方式和已确认 Pitfall；
2. **外部项目 Current**：当前代码、正式文档、配置契约、模块路径、Secret 名称和已验证参考实现；
3. **当前聊天**：本轮目标、临时参数、Working Assumption、用户补充资料和本次授权。

PKB 用于帮助 AI 理解用户希望怎样工作，但不能代替外部项目 Current。涉及现有项目的构建、修改或审查时，应先检索任务相关 PKB，再读取项目正式代码、治理文件或用户提供的参考资产，以现有实现确认具体契约。没有找到实现证据时，不得根据通用经验自行补造 Secret 名称、认证方式、字段契约、模块路径或 Runtime 结构。

用户明确要求“先检索 PKB”时，正式构建前应简要说明实际命中的 PKB 文件或段落、已读取的项目权威来源、准备沿用的既有契约，以及仍缺少证据的事项。

## 5. 知识吸收入口

任意 Chat 窗口都可以独立执行 PKB Review，不要求该窗口属于 Project，也不要求 Project Closeout 或 `PKB_SYNC_REQUIRED`。

默认独立入口为：

`SOURCE_MODE: CHAT_WINDOW_REVIEW`

如果窗口没有合格长期候选，Bridge 只输出 `NO_PKB_ACTION_REQUIRED`，不生成 Source Package。

正式项目收口后也可以使用 `PROJECT_CLOSEOUT_PACKAGE` 传递候选，但它只是兼容便利入口；项目收口、来源项目 branch、commit、clean worktree 和 `PKB_SYNC_REQUIRED` 等门禁只适用于该 source mode。

普通通识、一次性事实、外部项目 Current、进度、版本、下一步，以及 `INFERENCE`、`NEEDS_CONFIRMATION` 不进入 PKB。

存在合格候选时使用：

`$pkb-knowledge-absorption`

该 Skill 负责：

* 检查来源和仓库状态；
* 对候选内容进行文件归属判断；
* 读取现有 PKB 并查重；
* 优先合并或原位更新；
* 在确认后执行修改；
* 验证并按授权独立提交。

动态项目事实通过一次性 Source Package 提供，不永久写入 Skill 或本仓库正文。

## 6. 更新边界

只有以下变化需要更新本文：

* 仓库目的发生变化；
* Current 文件新增、删除、改名或职责变化；
* 正式知识吸收入口发生变化；
* Memory 与 Knowledge Current 文件的配合方式发生变化；
* 本地权威、GitHub 镜像或外部项目事实来源边界发生变化。

以下内容不进入本文：

* 某次知识吸收的候选、结果或 commit；
* 外部项目的当前状态和下一步；
* Notebook、脚本或数据集版本；
* Branch、Hash、run_id 和资源 ID；
* 临时维护事项或待办清单。

普通内容更新历史由本地 Git 保存，不在本文追加更新流水账。
