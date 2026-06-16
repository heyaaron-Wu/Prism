# 前端页面

Prism 包含多个前端页面，用于监控、研究、验证和系统状态展示。

## monitor

监控驾驶舱是主要操作视图。

当前包含：

- 持仓上下文
- 虚拟 / paper 上下文
- Shadow 候选
- Decision Card
- Detail Drawer
- 新闻与事件上下文
- 研究层预览

当前状态：基本稳定。

## market

市场页面用于展示市场概览、ETF、期货和板块相关信息。

当前状态：

- 桌面端布局稳定
- 移动端 grid 问题已处理
- 数字溢出和竖排问题已修复

## research

研究实验室是 research-only 页面。

它不是生产动作页面。

当前状态：

- research-only 边界清楚
- 板块汉化问题已修复
- 不影响 Recommendation 生产逻辑

## engineering

工程页面是主要验证与可观测性页面。

包含：

- Phase 3c 验证结果观察器
- runtime gate 解释
- Validator v2 shadow compare 展示
- Source Trace 与 Freshness Panel
- 数据源状态

## status

系统状态页展示服务和基础设施健康状态。

## login

登录页用于保护需要认证的正式页面。

部分公开只读页面可以在明确配置后免认证。

## 前端策略

Phase 3c 期间，前端改动应保持保守。

除非是严格 display-only 且不会引入新验证变量，否则不建议大改布局或增加复杂模块。
