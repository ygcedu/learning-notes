# EvanDbg/doubao-ime-win

## 项目背景

doubao-ime-win 是一个基于豆包 API 的 Windows 平台语音输入法工具，支持全局热键唤起、实时语音转写、Markdown 格式自动优化等功能。项目采用 Rust 语言开发，获得了 52 Stars 的关注。

## 核心技术/架构

项目采用 Rust (91.9%) 开发，辅以 Python (6.0%) 和 PowerShell (2.1%)。核心技术特点包括：

- **悬浮窗设计**：全局悬浮窗设计，可以在任何应用中唤起使用
- **全局热键**：支持自定义热键快速唤起语音输入
- **实时转写**：基于豆包 ASR 引擎，实现低延迟的语音转文字
- **Markdown 优化**：自动优化输出格式，支持 Markdown 语法

## 亮点与创新

1. **云端 ASR**：基于豆包 API 提供高精度的语音识别能力
2. **Windows 原生**：专为 Windows 平台设计，系统集成度高
3. **实时反馈**：支持边说边显示，提供实时转写体验
4. **格式优化**：自动处理标点符号和段落结构，输出符合 Markdown 规范

## 调研结论

doubao-ime-win 是 Windows 平台优秀的云端语音输入解决方案。与 macOS 的 TypeNo 项目形成互补：一个基于本地离线 ASR，一个基于云端 API。对于需要高精度识别和跨设备同步的场景，云端方案更有优势。

---

**项目信息**

- Stars: 52
- 语言：Rust (91.9%), Python (6.0%), PowerShell (2.1%)
- 最新版本：v1.1.1
- 地址：https://github.com/EvanDbg/doubao-ime-win
