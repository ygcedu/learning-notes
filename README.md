# Edlineas/aivectormemory

## 项目背景

aivectormemory 是一款基于 Model Context Protocol (MCP) 开发的 AI 记忆管理工具，专门为 Claude、OpenCode、Cursor 和主流 IDE 编程工具设计。该项目通过向量数据库技术解决 AI 在不同对话会话中「健忘」的问题，获得了 79 Stars 的关注。

## 核心技术/架构

项目采用多语言开发，包括 Python (37.4%)、Vue (14.2%)、JavaScript (14.0%)、Go (11.2%)、TypeScript (8.2%)、HTML (6.2%) 等。核心技术架构包括：

- **向量数据库**：基于向量相似度搜索实现语义级记忆检索
- **MCP 服务**：遵循 Model Context Protocol 标准，可与支持 MCP 的 AI 助手无缝对接
- **跨会话记忆**：支持持久化存储对话历史，实现跨会话的记忆保持
- **多平台支持**：兼容 OpenClaw、OpenCode、ClaudeCode 等多种 AI 编程代理

## 亮点与创新

1. **解决健忘问题**：传统 AI 对话在会话结束后会丢失所有上下文，该工具让 AI 能够回忆之前的对话
2. **语义检索**：基于向量相似度进行记忆检索，支持模糊匹配和语义关联
3. **持久化存储**：记忆数据持久化保存，支持长期记忆积累
4. **广泛兼容**：支持多种主流 AI 编程工具和 IDE

## 调研结论

aivectormemory 解决了 AI 编程助手的记忆持久化问题，是构建真正智能助手的基础设施。建议与 ktanaka101/mcp-server-duckdb 结合使用，可以构建完整的 AI 编程工作流：向量数据库存储对话记忆，DuckDB 处理数据分析。

---

**项目信息**

- Stars: 79
- 语言：Python, Vue, JavaScript, Go, TypeScript
- 最新版本：v2.0.8 (2026 年 3 月 26 日)
- 地址：https://github.com/Edlineas/aivectormemory