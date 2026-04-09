# claude-code-best/claude-code

## 项目背景

claude-code-best/claude-code 是一个对 Anthropic 官方 Claude Code CLI 进行逆向工程的开源项目，基于 Bun 构建，旨在提供一个可运行、可构建、可调试的 Claude Code 版本。该项目获得了 14.5k Stars 的高度关注，是当前 AI Agent 工具领域最热门的开源项目之一。

## 核心技术/架构

项目采用 TypeScript (99.8%) 开发，核心技术特点包括：

- **基于 Bun 运行时**：提供高性能执行环境，启动速度快，依赖安装简洁
- **完整逆向还原**：实现了 Claude Code 的核心功能，包括文件操作、代码执行、网络请求等
- **多 Provider 支持**：可对接不同的 LLM 提供商，不局限于 Anthropic 官方 API
- **30+ 工具集成**：支持文件系统操作、代码执行、终端命令、网络请求等多种工具

## 亮点与创新

1. **TypeScript 类型全修复**：解决了官方版本中的类型问题，提高企业级可靠性
2. **安全无毒**：lock 文件保真，可直接 `bun i` 安装依赖
3. **易于调试**：支持 `bun run dev` 启动开发模式
4. **完全开源**：可以深入理解 Claude Code 的内部工作机制

## 调研结论

claude-code-best/claude-code 是学习 AI Agent 工具开发的优秀开源案例。对于想要深入理解 Claude Code 架构或者基于它进行二次开发的开发者来说，这个项目提供了宝贵的参考价值。

建议结合 shareAI-lab/learn-claude-code 教学项目一起学习，可以系统性地掌握 Agent 框架的设计思路。

---

**项目信息**

- Stars: 14.5k
- 语言：TypeScript (99.8%)
- 地址：https://github.com/claude-code-best/claude-code
