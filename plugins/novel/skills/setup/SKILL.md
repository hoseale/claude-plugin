---
description: 初始化小说项目目录和设定模板
---

# 技能：setup-novel

初始化结构化小说项目环境：

**验证环境**：检查是否已存在项目结构。如存在，询问是否重新初始化（可能覆盖文件）。

1. 创建相应的文件夹结构：

- `00_Brainstorm` (杂记灵感)
- `01_World` (世界观设定)
- `02_Characters` (角色卡)
- `03_Outline` (大纲提要)
- `04_Chapters/` (正文目录，按卷组织)

2. 通用初始化步骤：
   - 在 `01_World` 创建 `world_setting.md`
   - 在 `03_Outline` 创建 `main_outline.md`
   - 复制`templates/`下的所有文件到根目录

3. 运行 `git init`（如未初始化），首次 commit "Initialize Novel Project"。

4. 通知用户初始化完成，提示使用 `/brainstorm` 和 `/write-chapter`。

## 错误处理

- 目录创建失败：通知用户并停止
- 文件写入失败：尝试备用方案
- git已初始化：跳过init，尝试提交
- 步骤失败：清理资源或通知用户
