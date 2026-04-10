# 7836246/cursor2api

## 项目背景

cursor2api 是一个将 Cursor Web Docs 免费 API 转换为 OpenAI/Anthropic 兼容格式的代理服务，获得了 1.7k Stars 的关注。

## 核心技术/架构

项目采用 TypeScript (46.6%) 开发，辅以 JavaScript (37.0%)、Vue (12.3%)、CSS (2.4%)。核心技术特点包括：

- **API 转换**：将 Cursor API 转换为标准 OpenAI/Anthropic 格式
- **工具支持**：提供 Claude Code 工具支持
- **图片支持**：支持图片处理能力
- **代理服务**：作为中间层转发请求

## 亮点与创新

1. **免费使用**：利用 Cursor Web Docs 免费 API
2. **格式兼容**：转换为标准 API 格式，兼容更多客户端
3. **工具扩展**：支持 Claude Code 工具调用

## 调研结论

cursor2api 提供了一种低成本使用 Cursor AI 能力的方式。但需要注意其依赖 Cursor Web Docs API，可能存在稳定性风险。对于有更高稳定性要求的场景，建议直接使用官方 API 或 Claude Code、Codex 等本地代理。

---

**项目信息**

- Stars: 1.7k
- 语言：TypeScript (46.6%), JavaScript (37.0%), Vue (12.3%)
- 最新版本：v2.7.8 (2026年3月27日)
- 许可证：MIT
- 地址：https://github.com/7836246/cursor2api