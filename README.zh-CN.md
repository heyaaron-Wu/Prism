<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="Logo/prism-logo-light.png">
    <source media="(prefers-color-scheme: light)" srcset="Logo/prism-logo-dark.jpg">
    <img src="Logo/prism-logo-dark.jpg" width="180" alt="Prism logo">
  </picture>
</p>

<h1 align="center">Prism</h1>

<p align="center">
  面向工程可观测性、决策解释、验证流程和研究型市场监控的<br />
  human-in-the-loop AI 系统。
</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="docs/architecture.zh-CN.md">系统架构</a> ·
  <a href="docs/phase3c-validation.zh-CN.md">验证流程</a> ·
  <a href="docs/safety-boundaries.zh-CN.md">安全边界</a> ·
  <a href="docs/roadmap.zh-CN.md">路线图</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Human--in--the--loop-AI%20System-blue" alt="Human-in-the-loop AI System" />
  <img src="https://img.shields.io/badge/Focus-Observability-green" alt="Observability" />
  <img src="https://img.shields.io/badge/Focus-Decision%20Explainability-purple" alt="Decision Explainability" />
  <img src="https://img.shields.io/badge/Docs-Bilingual-lightgrey" alt="Bilingual Documentation" />
</p>

---

Prism 是一个 human-in-the-loop 的 AI 系统，重点关注工程可观测性、决策解释、验证流程，以及研究导向的市场监控。

项目的核心原则很简单：AI 可以帮助整理市场信号、验证结果、风险上下文和系统状态，但真实决策必须保持可解释、可审计，并由人类手动控制。

## 项目重点

Prism 关注：

- 半自动 AI 系统的工程可观测性
- 针对候选标的和持仓的 Decision Card 决策解释
- 分阶段验证流程
- runtime 与 EOD 验证可视化
- 数据源新鲜度与来源追踪
- 财报、SEC 事件、板块上下文和 ETF flow 等事件情报
- 明确区分真实持仓、虚拟持仓、Shadow 候选、research-only 项和 news-only 项

## Prism 不做什么

Prism 不定位为完全自动交易机器人。

它不试图：

- 在没有人工确认的情况下自动执行真实交易
- 提供金融投资建议
- 替代风险管理或人工复核
- 把 display-only 研究信号当作交易 gate
- 让实验性 validator 直接影响生产 clean-day 计数

## 前端视图

Prism 包含工程状态、市场概览、研究、监控和系统健康等前端视图。

公开部署网址不会列在本仓库中。后续可以在审查后加入截图和经过筛选的说明文档。

## 仓库用途

本仓库当前用于 Prism 的公开项目概览，记录系统架构、验证流程、安全边界、项目模块和路线图。

生产密钥、券商细节、服务器配置、私有日志、`.env` 文件、webhook、账户凭据和敏感交易数据都不会放入本仓库。

## 文档

English:

- [Architecture](docs/architecture.md)
- [Phase 3c Validation](docs/phase3c-validation.md)
- [Decision Cards](docs/decision-card.md)
- [Event Intelligence](docs/event-intelligence.md)
- [Frontend Pages](docs/frontend-pages.md)
- [Safety Boundaries](docs/safety-boundaries.md)
- [Roadmap](docs/roadmap.md)

中文：

- [系统架构](docs/architecture.zh-CN.md)
- [Phase 3c 验证](docs/phase3c-validation.zh-CN.md)
- [Decision Card 决策解释卡](docs/decision-card.zh-CN.md)
- [Event Intelligence 事件情报](docs/event-intelligence.zh-CN.md)
- [前端页面](docs/frontend-pages.zh-CN.md)
- [安全边界](docs/safety-boundaries.zh-CN.md)
- [路线图](docs/roadmap.zh-CN.md)

## 双语维护原则

英文和中文文档应同步修订。当项目范围、安全边界、验证设计或路线图发生变化时，两种语言版本应在同一次维护中一起更新。

## License

License 信息会在公开仓库成熟后再最终确定。

## Disclaimer

本项目用于研究、工程可观测性和 human-in-the-loop 决策支持。它不是金融建议，也不应在没有独立复核和风险控制的情况下作为真实交易依据。
