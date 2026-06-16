# Phase 3c 验证

Phase 3c 是 Prism 当前的 Shadow 验证阶段。

目标是在进入后续阶段前，观察系统是否能在严格条件下连续通过完整验证日。

## 当前状态

- Phase：3c Shadow
- Clean day progress：0/5
- Phase 3d：locked
- 手动补计：不允许

## Clean day 条件

Clean day 不只看 EOD snapshot。

必须同时满足：

- scheduled EOD 有效
- full-day coverage 有效
- coverage 阈值通过
- EOD snapshot P0/P1/P2 通过
- runtime shadow P0/P1 全天通过
- dedupe guard 没有跳过
- manual run 不参与计数

## 关键区别

EOD Snapshot PASS 不等于 Clean Day PASS。

此前有一次结果显示 EOD snapshot 通过，但 runtime shadow gate 未完全通过，因此没有计入 clean day。

## Runtime P0 审计结论

已完成一次 runtime P0 failure explorer。结论显示，这批失败主要来自旧 runtime 对齐与日志 payload 不足，不是 display-only 模块污染，也没有改变 Phase 3c 标准。

## Validator v2 角色

Validator v2 当前仅用于 shadow compare。

它不会：

- 替换 production validator
- 影响 clean-day 计数
- 覆盖 Phase 3c 规则
- 因自身 PASS 而直接让某日计入

## 当前策略

当前策略是等待下一次 scheduled EOD，观察 EOD snapshot 与全天 runtime gate 是否同时通过。

不允许手动补计 clean day。
