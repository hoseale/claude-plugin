# 项目说明

本项目为结构化小说写作项目，使用 Claude Code 进行辅助创作。

## 工作流程

1. 使用 `/brainstorm` 进行大纲创作和角色设定
2. 使用 `/write-chapter` 撰写章节正文
3. 使用 `/review` 进行章节审核
4. 使用 `/volume-skeleton` 进行分卷骨架设计
5. 使用 `/volume-outline` 对指定卷号进行分卷细纲架构
6. 使用 `/chapter-skeleton` 对指定卷号进行章节骨架设计
7. 使用 `/chapter-outline` 对指定卷号及章节号范围进行章节细纲架构

## 目录说明

```
├── 00_Brainstorm/              # 杂记灵感
│   └── 灵感片段、场景描述、零散想法
│
├── 01_World/                   # 世界观设定
│   └── world_setting.md
│
├── 02_Characters/              # 角色卡
│   └── 角色设定文档
│
├── 03_Outline/                 # 大纲提要
│   ├── main_outline.md         # 主线大纲（全书逻辑）
│
│   ├── volume/                 # ⭐ 分卷体系（结构 + 卷大纲）
│   │   ├── structure.md        # 全书分卷骨架
│   │   ├── volume_01.md        # 第1卷细纲
│   │   ├── volume_02.md        # 第2卷细纲
│
│   ├── chapter/                # ⭐ 章节体系（结构 + 细纲）
│   │   ├── 01_structure.md     # 第1卷章节骨架
│   │   ├── 01_volume.md        # 第1卷章节细纲
│   │   ├── 02_structure.md
│   │   ├── 02_volume.md
│
│   └── summary.md              # 章节概要汇总
│
├── 04_Chapters/                # 正文目录
│   ├── volume_1/               # 各卷正文
│   │   ├── chapter_01.md       # 第1卷第1章
│   │   └── chapter_02.md
│
└── style_guide.md              # 风格指南
```

## 命名规范

- 章节文件：`chapter_XX.md`（XX 为两位数字，如 01, 02）
- 卷目录：`volume_X`（X 为数字）
- 细纲文件：`volume_X_detailed.md`
