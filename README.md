# Autogenesis - 自进化 Agent 协议

## 项目背景

Autogenesis 是一个面向 LLM（大语言模型）代理系统的**自演进协议和运行时**，于 2026 年 4 月发布在 arXiv 上（arXiv:2604.15034）。该项目针对当前 Agent 协议（如 A2A、MCP）在跨实体生命周期管理、版本追踪和安全演进更新接口方面的不足，提出了创新的解决方案。

项目由 Wentao Zhang、Zhe Zhao、Haibin Wen、Yingcheng Wu、Ming Yin、Bo An 和 Mengdi Wang 等研究者共同开发，采用 MIT 许可证开源，目前在 GitHub 上获得 18 颗星标。

## 核心技术架构

Autogenesis Protocol（AGP）采用**双层架构设计**，将「什么会演进」与「如何演进」解耦，这是其核心创新点。

### RSPL（资源子协议层）

RSPL 将系统中的各类组件建模为协议注册的资源，包括提示词（Prompts）、代理（Agents）、工具（Tools）、环境（Environments）和内存（Memory）。每种资源都具有明确的**状态**、**生命周期**和**版本化接口**，使得资源的管理变得可追踪和可控。这种设计使得开发者可以独立地对某一类资源进行升级或替换，而不影响系统的其他部分。

### SEPL（自进化协议层）

SEPL 定义了闭环操作符接口，支持三个核心操作：提议改进（Propose）、评估改进（Assess）和提交改进（Commit）。这一层还提供了可审计的演进谱系（Lineage）和回滚（Rollback）能力，确保系统在自我改进过程中的安全性和可追溯性。当 Agent 在执行过程中发现问题时，可以回滚到之前的状态，避免错误改进导致的系统崩溃。

### AGS（Autogenesis System）

基于 AGP 协议，项目实现了一个完整的自进化多代理系统 AGS。该系统能够在执行过程中动态实例化、检索和优化协议注册的资源，实现真正的运行时自适应。

## 迭代循环机制

Autogenesis 支持一个四阶段的迭代循环来实现持续自我改进。第一阶段是 Act（行动），代理利用 LLM 和可用工具产生动作或输出。第二阶段是 Observe（观察），系统捕获执行结果、轨迹、中间推理过程和环境反馈。第三阶段是 Optimize（优化），使用优化器（如反射或强化学习方法）更新提示词、解决方案或变量。第四阶段是 Remember（记忆），将摘要、洞察和记录持久化到内存中，供后续步骤和会话使用。

## 核心组件

项目代码采用 Python 实现（占比 99.6%），主要包含以下核心模块。Agent 模块（src/agent/）包含运行时逻辑，负责决定下一步做什么，包括规划、工具调用和领域代理等。Tool 模块（src/tool/）向代理暴露各种可调用能力，包括工作流工具和默认工具。Environment 模块（src/environment/）提供状态化接口，工具和代理可以与文件系统、交易回测环境、浏览器或移动环境等进行交互。Memory 模块（src/memory/）实现会话和事件内存系统，用于摘要、洞察和长期状态管理。Optimizer 模块（src/optimizer/）实现自改进算法，将反馈转化为更新的提示词、解决方案或变量，支持反射、GRPO、Reinforce++ 等多种方法。此外还有 Tracing 和 Versioning 模块用于记录轨迹和管理跨运行的迭代产物，Config 系统采用类似 MMEngine 的配置方式，以一致的方式组合代理、工具、环境、内存和模型。

## 与现有协议的对比

现有的 A2A（Agent-to-Agent）协议和 MCP（Model Context Protocol）主要关注代理之间的通信和工具调用，但缺乏对跨实体生命周期管理、版本追踪和安全演进更新接口的规范。这导致了系统倾向于单体组合，产生大量脆弱的胶水代码。Autogenesis 的创新之处在于，它不仅定义了资源如何被注册和管理，还定义了资源如何能够安全地自我改进，通过版本控制和回滚机制确保演进过程的可靠性。

## 设计目标

项目有三个核心设计目标。可组合性（Composable）意味着可以添加或替换代理、工具、环境、内存系统和优化器，而无需重写整个技术栈。可检查性（Inspectable）通过结构化的轨迹和内存事件，使分析失败和改进步骤变得更加容易。可演进性（Evolvable）通过显式优化器和持久化内存支持迭代精炼，而非一次性推理。

## 项目状态与使用

目前代码库处于**活跃重构和优化阶段**。`examples/run_tool_calling_agent.py` 是可运行的工具调用代理示例，其他代理作为重构工作的一部分正在逐步稳定。使用前需要参考 `scripts/INSTALL.md` 安装依赖，并将 `.env.template` 复制为 `.env` 后设置环境变量。运行示例命令为 `python examples/run_tool_calling_agent.py --config configs/tool_calling_agent.py`。

## 调研结论

Autogenesis 代表了 LLM Agent 协议领域的一个重要研究方向。它通过双层协议架构，将资源管理与自进化机制分离，为构建可自我改进的 Agent 系统提供了理论基础和工程实践。尽管项目目前仍处于早期开发阶段，其设计理念和实现思路对于未来 Agent 协议的发展具有重要参考价值。特别是在需要长视野规划和异构资源工具使用的复杂任务场景中，这种自进化能力可能会带来显著的性能提升。

## 参考资料

- [Autogenesis: A Self-Evolving Agent Protocol - arXiv](https://arxiv.org/abs/2604.15034)
- [GitHub - DVampire/Autogenesis](https://github.com/DVampire/Autogenesis)
- [会自己进化的 Agent 很酷，直到你发现考卷是它自己出的 - 思维编译](https://weixin.sogou.com/)
- [MCP vs A2A：塑造 AI Agent 生态的两大协议对比](https://devtk.ai/zh/blog/mcp-vs-a2a-comparison-2026/)