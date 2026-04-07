# 项目说明

本项目为结构化小说写作项目，使用 Claude Code 进行辅助创作。

## 工作流程

1. 使用 `/brainstorm` 进行大纲创作和角色设定
2. 使用 `/write-chapter` 撰写章节正文
3. 使用 `/review` 进行章节审核
4. 使用 `/migrate-volume` 进行卷迁移
5. 使用 `/compress-memory` 进行内存压缩，释放空间
6. 使用 `/volume-outline` 进行分卷大纲创作

## 目录说明

```
├── 00_Brainstorm/      # 杂记灵感
│   └── 灵感片段、场景描述、零散想法
├── 01_World/           # 世界观设定
│   └── world_setting.md
├── 02_Characters/      # 角色卡
│   └── 角色设定文档
├── 03_Outline/         # 大纲提要
│   ├── main_outline.md      # 主线大纲
│   ├── volume_structure.md  # 分卷大纲（分卷时）
│   ├── volume_X_detailed.md # 各卷细纲（分卷时）
│   ├── chapter_outline.md   # 章节大纲（不分卷时）
│   └── summary.md           # 章节概要汇总
├── 04_Chapters/        # 正文目录
│   ├── volume_1/         # 分卷时：各卷正文
│   │   ├── chapter_01.md
│   │   └── chapter_02.md
│   └── chapter_01.md     # 不分卷时：直接放置章节
│   └── chapter_02.md
└── style_guide.md       # 风格指南
```

## 命名规范

- 章节文件：`chapter_XX.md`（XX 为两位数字，如 01, 02）
- 卷目录：`volume_X`（X 为数字）
- 细纲文件：`volume_X_detailed.md`
