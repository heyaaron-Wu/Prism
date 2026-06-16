# Phase 3c 验证设计

本文把 Phase 3c 作为 Prism 内部的 shadow-validation 设计模式来说明。公开文档重点解释验证概念和安全边界，不记录私有 runtime 计数、当前 clean-day 进度、原始日志或运行事故细节。

## 目的

分阶段验证用于防止 AI 辅助系统过快地从观察状态进入更强的运行信任状态。

目标是在保持实验性模块和 display-only 模块不具备生产权威的前提下，评估系统是否能在严格条件下完成完整验证日。

## Clean day 概念

Clean day 不只是一个 EOD 状态消息。它是更严格的验收概念，要求多个条件在整个验证窗口内同时成立。

公开安全版 clean-day 设计可以包含：

- scheduled validation run 有效，
- full-day coverage 有效，
- coverage 阈值满足要求，
- EOD snapshot 通过所需级别检查，
- runtime shadow checks 在验证窗口内通过，
- deduplication guard 没有跳过或重复计数，
- manual run 不被当作 scheduled validation 证据。

## 关键区别

```text
EOD Snapshot PASS 不等于 Clean Day PASS。
```

EOD snapshot 可能显示最终状态可接受，但更严格的 clean-day gate 仍可能因为某个 runtime 条件没有在整个验证窗口内持续成立而失败。

这个区别很重要，因为 Prism 把验证视为可审计流程，而不是单条最终消息。

## Runtime gate 设计

Runtime validation 用来发现最终 EOD snapshot 中不一定可见的问题。

Runtime gate 概念包括：

- production 与 shadow 决策对齐，
- blocker 一致性，
- stale-source 处理，
- missing-payload 检测，
- actionability 检查，
- display-only contamination 检查，
- validation trace 完整性。

公开文档只解释这些概念的设计层级，不发布私有 runtime 失败次数、原始失败行、内部标的或运行事故 payload。

## Validator v2 角色

在公开设计中，Validator v2 被视为 shadow-compare 层。

它不会：

- 替代 production validator，
- 削弱 production validation rules，
- 直接计入某个 validation day，
- 覆盖 production safety boundaries，
- 把 research-only 或 display-only 信息变成 production gates。

## Manual-run 原则

Manual run 可以用于调试和检查，但不应该被计入 scheduled validation 证据。

这样可以避免误补计、重复计数，或者产生无法与 scheduled run 对比的验证结果。

## 公开范围边界

本文刻意不公开：

- 当前 clean-day 进度，
- 原始验证失败次数，
- 私有 runtime 日志，
- 生产标的或账户细节，
- 内部服务器路径，
- 券商特定行为，
- 私有 validator payload。

本文的作用是解释验证设计，而不是作为实时运行报告。
