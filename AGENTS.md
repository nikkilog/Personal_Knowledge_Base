# Personal Knowledge Base Repository Rules

本文件仅适用于 Personal_Knowledge_Base 仓库。

## Storage and Version Control

- Personal_Knowledge_Base 仅保存在本机。
- 本地文件是唯一编辑源。
- 仅使用本地 Git 管理版本历史。
- 不得上传、同步或备份到 Google Drive、iCloud、GitHub、OneDrive、Dropbox 或其他云端。
- 不得复制到 CAH 或其他项目仓库。
- 不得放入共享目录。
- 仅允许加密的离线备份。

## Credentials and Privacy

- 不得保存 Secret、Token、密码、认证 JSON、私钥或其他凭据值。
- AI 推断出的个人信息不得直接写入，必须先由用户确认。

## Access Rules

- 普通代码任务不得默认读取 PERSONAL_CONTEXT.md。
- 只有用户明确要求，或任务直接依赖个人长期背景时，才允许读取 PERSONAL_CONTEXT.md。

## Editing Rules

- 修改必须原位进行。
- 禁止创建 final、updated、fixed、new、最新版、(1) 等平行副本。

## Content Boundaries

- PERSONAL_CONTEXT.md 保存长期稳定的个人背景和偏好。
- PITFALL_LOG.md 保存经过验证、可跨任务复用且已脱敏的经验。
- 临时状态、项目进度和项目专属规则应保存在对应项目仓库，不进入本知识库。

## Project Closeout Knowledge Absorption

- 正式项目收口后，应主动检查是否产生新的长期偏好、协作规则或可复用 Pitfall，不依赖用户重复提醒。
- 进入本知识库前，项目仓库必须先完成提交或必要合并，并保持工作树干净。
- 项目仓库与本知识库使用独立仓库、独立 Diff 和独立 commit；不得让两个仓库同时存在未提交修改。
- 先查重，再合并或更新 Current 文件；已完整覆盖时不得重复新增或创建空提交。
- 项目专属事实、版本、资源标识和临时状态留在项目仓库，不得进入本知识库。
- 本知识库更新后应独立验证并提交；不得 push、发布或进行任何云同步。
