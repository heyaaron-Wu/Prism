# Prism 系统架构

Prism 采用分层架构，用来清楚区分用户界面、解释模块、验证模块、上下文模块和安全边界。

## 核心思路

Prism 是一个 human-in-the-loop AI 系统。它帮助用户理解系统状态、验证结果、数据来源和候选对象的上下文，但不会把展示信息直接等同于生产动作。

## 高层结构

- UI 层：monitor、market、research、engineering、status
- 解释层：Decision Cards、Event Intelligence、Source Trace、Freshness Panel
- 验证层：Phase 3c EOD Viewer、Runtime P0/P1 checks、Production validator、Validator v2 shadow compare
- 上下文层：DecisionContext v1 skeleton、account_context、candidate_context、risk_context、event_context、freshness_context、source_trace、safety_flags

## 运行身份

Prism 是当前项目的 canonical identity。历史遗留命名会在后续阶段逐步清理，但 Phase 3c 期间不会为了清理命名而引入新的运行变量。

## 设计原则

- 观察层与生产层分离
- 解释层与验证层分离
- 研究信息与正式判断分离
- 文档、页面和状态展示必须保持可审计
- 公开仓库不包含敏感配置或私有日志
