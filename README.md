# Obsidian AI 架构师 Skills (ObsidianArchSkills)

这是一个基于 MCP (Model Context Protocol) 的 AI 技能集，旨在将 **VS Code 开发环境** 与 **Obsidian 知识库** 深度融合。它赋予了 AI “架构师”和“交互分析师”的人格，能够自动生成、维护并解读项目的架构逻辑图。

通过这套 Skills，你可以让 AI 自动分析你的代码库，并在 Obsidian 中生成可交互的、动态的架构图（Canvas），实现“架构即代码”的可视化管理。

## ✨ 核心功能

*   **🤖 自动化架构生成**: 一键扫描项目，生成全局架构概览图。
*   **🔍 深度模块分析**: 自动识别核心模块，生成详细的内部类结构和依赖图。
*   **⏱️ 动态序列图**: 针对关键业务场景（如“下单流程”），生成清晰的时序交互图。
*   **🔄 双向同步**: 支持从 Obsidian 画布反向修改代码（如重构命名），实现架构驱动开发。
*   **💬 智能架构问答**: 基于生成的架构图，回答关于系统设计、风险和逻辑的问题。

## 🚀 快速开始

### 前置要求
1.  **Obsidian**: 安装并配置好 Obsidian。
2.  **MCP Server**: 确保你的 AI 助手环境（如 Cursor, VS Code Copilot 等）已配置 `obsidian-mcp-server` 和 `filesystem` 权限。
3.  **JSON Canvas**: 本项目遵循官方 [JSON Canvas](https://jsoncanvas.org/) 规范。

### 安装
将 `ObsidianArchSkills` 文件夹复制到你的 AI 助手配置的 Skills 目录或工作区中。

### 使用指令

在 AI 对话框中，你可以使用以下指令：

| 指令 | 描述 |
| :--- | :--- |
| `/init` | **初始化项目**：在 Obsidian 中创建项目文件夹，并自动生成全套架构文档（全局图+模块详情+核心序列图）。 |
| `/arch` | **生成/更新架构图**：手动触发架构分析，更新 `architecture.canvas`。 |
| `/seq` | **生成序列图**：针对特定场景生成交互图，例如 `/seq 用户登录流程`。 |
| `/sync` | **同步代码**：将 Obsidian 画布中的变更应用到代码库。 |
| `/ask` | **架构解读**：询问关于当前架构的问题。 |

## 📂 项目结构

```text
ObsidianArchSkills/
├── SKILL.md                # 核心技能定义与执行逻辑
├── README.md               # 项目说明文档
└── prompts/                # AI 角色与任务提示词
    ├── architect_core.md   # [架构总师] 提示词：负责静态结构分析
    ├── interaction_core.md # [交互分析总师] 提示词：负责动态时序分析
    └── canvas_spec.md      # JSON Canvas 官方规范：防止 AI 幻觉
```

## 🛡️ 防幻觉机制

本项目集成了官方的 **JSON Canvas Specification 1.0**。在生成任何图形文件之前，AI 都会强制读取规范文档，确保生成的 `.canvas` 文件格式绝对正确，可在 Obsidian 中完美打开。

## 🤝 贡献

欢迎提交 Issue 或 Pull Request 来改进提示词或增加新的技能！
