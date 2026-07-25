# Personal Knowledge Base

> 状态：Current
> 最后复核：2026-07-24

## 1. 仓库目的

本仓库用于保存长期稳定、能够跨对话和跨项目复用的个人工作上下文与经验。

它帮助新的 AI、协作者或未来的自己，在不依赖历史聊天记录的情况下，理解：

* 用户长期从事的业务和工作范围；
* 用户偏好的思考、沟通和交付方式；
* 跨项目适用的操作习惯；
* 已真实发生、值得防止复发的通用 Pitfall；
* 本知识库自身的维护边界。

本仓库不是外部项目的状态仓库，不保存外部项目的当前进度、版本、资源标识、运行记录或下一步。

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

### `PERSONAL_CONTEXT.md`

长期稳定的个人背景、工作偏好和默认协作方式。

用于帮助 AI 在 AGENTS.md 允许的范围内选择更合适的方案，但不构成删除、提交、发布或其他高影响操作的授权。

### `PITFALL_LOG.md`

已经真实发生、根因足够明确、可跨任务复用且具备验证方式的故障与修复经验。

Pitfall 编号长期稳定；条目合并、迁移或废弃时不得重新编号或复用旧编号。

## 3. 文件配合顺序

处理依赖个人长期知识的任务时，按以下顺序使用：

1. 读取 `AGENTS.md`，确定仓库边界和强制规则；
2. 读取 `PROJECT.md`，确认当前正式资产和文件职责；
3. 按任务需要读取 `PERSONAL_CONTEXT.md`；
4. 按任务涉及的系统或问题类型查阅 `PITFALL_LOG.md`。

各文件应保持唯一职责。相同知识不得在多个文件中重复保存完整正文；需要关联时优先使用稳定条目名称或 Pitfall 编号引用。

## 4. 知识吸收入口

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

## 5. 更新边界

只有以下变化需要更新本文：

* 仓库目的发生变化；
* Current 文件新增、删除、改名或职责变化；
* 正式知识吸收入口发生变化；
* 三个核心知识文件的配合方式发生变化。

以下内容不进入本文：

* 某次知识吸收的候选、结果或 commit；
* 外部项目的当前状态和下一步；
* Notebook、脚本或数据集版本；
* Branch、Hash、run_id 和资源 ID；
* 临时维护事项或待办清单。

普通内容更新历史由本地 Git 保存，不在本文追加更新流水账。
