# Personal Knowledge Base

## Purpose

仅在本机保存长期稳定的个人背景、偏好，以及经过验证、可跨任务复用且已脱敏的经验。

## Current Files

- PERSONAL_CONTEXT.md
- PITFALL_LOG.md

## Editing Rules

- 本地文件是唯一编辑源。
- 仅使用本地 Git 管理版本历史。
- 所有修改必须原位进行。
- 修改前检查 Git 状态。
- 禁止创建 final、updated、fixed、new、最新版、(1) 等平行副本。
- 普通代码任务不得默认读取 PERSONAL_CONTEXT.md。
- 只有用户明确要求，或任务直接依赖个人长期背景时，才允许读取 PERSONAL_CONTEXT.md。

## Privacy

- Personal_Knowledge_Base 仅保存在本机。
- 不得上传、同步或备份到 Google Drive、iCloud、GitHub、OneDrive、Dropbox 或其他云端。
- 不得复制到 CAH 或其他项目仓库，也不得放入共享目录。
- 不得保存 Secret、Token、密码、认证 JSON、私钥或其他凭据值。
- 仅允许加密的离线备份。

## Content Boundaries

- PERSONAL_CONTEXT.md 保存长期稳定的个人背景和偏好。
- PITFALL_LOG.md 保存经过验证、可跨任务复用且已脱敏的经验。
- 临时状态、项目进度和项目专属规则应保存在对应项目仓库，不进入本知识库。
- AI 推断出的个人信息不得直接写入，必须先由用户确认。

## Maintenance Workflow

长期知识维护流程：

项目工作或其他来源产生长期知识 → 识别偏好与 Pitfall → 项目仓库先收口并保持工作树干净 → 本知识库查重 → 更新 Current 文件 → 独立验证 → 独立 Git commit。

- 当前维护方式包括主动吸收长期知识，不依赖用户重复提醒。
- 本知识库不是项目状态仓库，也不是云端知识库；项目现场和一次性状态留在对应项目仓库。
- Git 保存普通修改历史；`archive/` 只保存具有独立追溯价值的旧知识资产。
- 本知识库与来源项目分别审查、验证和提交，不共享 commit，也不同时保留未提交修改。
