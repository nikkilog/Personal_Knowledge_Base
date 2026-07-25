# PKB Knowledge Absorption Bridge Prompt — Standalone Chat Review

请根据本窗口从开始到现在的完整对话内容，**独立判断**是否存在值得进入 Personal Knowledge Base 的长期知识。

本 Prompt 可以用于任何 Chat 窗口：

- 可以是项目窗口，也可以完全不是项目；
- 可以是很长的工作窗口，也可以是很短的问题；
- 不要求已经执行 Project Closeout；
- 不要求存在 `PKB_SYNC_REQUIRED`；
- 不要求来源项目已经 commit 或 worktree clean；
- 项目收口结果如果存在，只作为额外证据，不是前置条件。

## 独立判断结果

只有两种输出：

- 本窗口没有合格长期知识：只输出 `NO_PKB_ACTION_REQUIRED`
- 本窗口存在至少一项合格长期知识：生成下述 Codex 调用包

不要在当前聊天窗口修改 `Personal_Knowledge_Base`。
不要让我手工填写参数。
不要先输出分析、候选表或草稿。
不要生成第二份 Source Package。
最终只输出一个纯文本代码块，代码块前后不要添加解释。

## 调用包固定参数

```text
$pkb-knowledge-absorption

PACKAGE_SCHEMA_VERSION:
1

TARGET_REPO_PATH:
/Users/nikki/Documents/AI_Workspace/Personal_Knowledge_Base

EXPECTED_BRANCH:
main

EXPECTED_DIRTY_FILES:
NONE

SOURCE_MODE:
CHAT_WINDOW_REVIEW

KNOWLEDGE_FOCUS:
ALL

EXECUTION_MODE:
AUDIT_THEN_CONFIRM

COMMIT_MODE:
COMMIT_AFTER_VALIDATION
```

`SOURCE_PACKAGE` 只传递本窗口的动态事实，不重复 Skill 中已经定义的稳定治理规则。

## 自动审查范围

自动判断本窗口是否产生以下任一长期候选：

1. 稳定的个人背景、偏好、沟通方式、交付习惯或验收偏好；
2. 跨项目、跨窗口可复用的工作方法、判断规则或默认协作方式；
3. 已实际发生、症状明确、根因充分建立且处理方式已验证的通用 Pitfall；
4. PKB 自身的操作、路由、隐私、去重或维护规则；
5. 用户明确要求长期保留，且删除当前项目或话题名称后仍然成立的知识。

对所有窗口进行审查，不等于所有窗口都必须写入 PKB。以下情况应输出 `NO_PKB_ACTION_REQUIRED`：

- 只有一次性问答或临时事实；
- 只有一般背景知识，没有形成用户长期偏好、可复用方法或已验证 Pitfall；
- 内容已经明显属于单个项目 Current、进度、版本或业务规则；
- 只有推断，没有用户确认或实际执行依据；
- 没有任何候选满足正式事实等级要求。

## 事实等级

事实等级只使用：

- `USER_CONFIRMED`
- `USER_PROVIDED`
- `OBSERVED_WORKFLOW`
- `INFERENCE`
- `NEEDS_CONFIRMATION`

Source Package 只是信息传递载体，不是独立证据。不得因为整理后的措辞更确定，就把内容升级为 `USER_CONFIRMED`。

只有以下内容可以作为正式候选：

- `USER_CONFIRMED`
- `USER_PROVIDED`
- 有明确实际执行依据的 `OBSERVED_WORKFLOW`

`INFERENCE` 和 `NEEDS_CONFIRMATION` 只能交给 Codex 标记，不得要求直接写入 PKB。

## 排除范围

不得把以下内容作为 PKB 正文候选：

- 当前项目进度或唯一下一步；
- Current 文件、版本、branch、commit、Hash 或 run_id；
- Sheet、Folder 或其他资源 ID；
- Secret 值；
- 绝对项目路径；
- 单次任务状态；
- 只适用于当前项目的业务规则；
- 可以直接从来源项目仓库读取的项目事实；
- 当前价格、即时新闻或可能快速变化的事实；
- 普通通识答案本身；
- 未经用户确认的个人推断。

必要的 Secret 名称或非敏感配置键可以作为长期配置约定候选，但不得包含 Secret 值。

## 最终输出格式

```text
$pkb-knowledge-absorption

PACKAGE_SCHEMA_VERSION:
1

TARGET_REPO_PATH:
/Users/nikki/Documents/AI_Workspace/Personal_Knowledge_Base

EXPECTED_BRANCH:
main

EXPECTED_DIRTY_FILES:
NONE

SOURCE_MODE:
CHAT_WINDOW_REVIEW

KNOWLEDGE_FOCUS:
ALL

EXECUTION_MODE:
AUDIT_THEN_CONFIRM

COMMIT_MODE:
COMMIT_AFTER_VALIDATION

SOURCE_PACKAGE:

PKB_ABSORPTION_RECOMMENDED:
YES

本窗口的最小背景：
<自动填写完整内容>

可选的项目或收口背景：
<存在时自动填写；不存在时写 NONE>

Personal Context 候选：
<自动填写；没有时写 NONE>

Pitfall 候选：
<自动填写；没有时写 NONE>

PKB 操作规则候选：
<自动填写；没有时写 NONE>

可能已经覆盖的内容：
<自动填写；无法从当前窗口判断时写 NEEDS_REPOSITORY_CHECK>

吸收前必须剥离的话题或项目专属细节：
<自动填写；没有时写 NONE>

明确不进入 PKB 的本窗口内容：
<自动填写>

事实等级与不确定项：
<逐项自动填写>

要求 Codex：

- 先读取 PKB 的 AGENTS.md、PROJECT.md、PERSONAL_CONTEXT.md 和 PITFALL_LOG.md；
- 第一阶段只读审计，逐候选完成 owner routing、查重和唯一 bounded execution package；
- 优先 MERGE_INTO_EXISTING_ENTRY，其次 UPDATE_EXISTING，最后才 CREATE_NEW_ENTRY；
- 已完整覆盖的内容标记 ALREADY_COVERED，不修改文件、不创建空提交；
- 单个候选证据不足时只处理该候选，不阻塞其他有效候选；
- 未经用户确认不得修改、删除、迁移、stage 或 commit；
- 确认后只修改获批文件和条目；
- 验证后才允许独立提交；
- 不要求存在 Project Closeout 或 PKB_SYNC_REQUIRED；
- 不修改来源项目、Workspace_Control 或其他仓库；
- 不 push、不发布、不进行云同步。
```

最终不得保留任何 `<...>` 占位符；必须用本窗口真实内容填写。没有内容的候选区写 `NONE`。
