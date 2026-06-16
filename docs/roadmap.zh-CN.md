# 路线图

本路线图描述 Prism 的公开项目方向，并区分文档、展示、验证和未来生产变更。

## 当前阶段

- Phase：3c Shadow validation
- Progress：0/5 clean days
- Status：等待下一次 scheduled EOD 验证

## 已完成或基本完成

- 服务边界稳定
- 主要前端页面
- Decision Card 解释层
- 财报、SEC、板块和 ETF 上下文
- Source Trace / Freshness Panel
- Phase 3c EOD Viewer
- Runtime P0 解释与审计链路
- Validator v2 schema 与 shadow compare
- DecisionContext v1 skeleton
- legacy 命名清理 inventory

## 近期重点

- 等待下一次 scheduled EOD
- 观察 runtime P0/P1 与 EOD snapshot 是否同时通过
- 保持 Phase 3c clean-day 规则不变
- 保持 Validator v2 shadow-only
- 验证期内避免新增运行变量

## 延后清理

legacy 命名清理已记录，但暂缓执行。

清理阶段建议：

1. Phase 3c 期间只记录
2. 稳定 EOD 后只做低风险文案清理
3. Phase 3c 5/5 且人工批准后再做运行相关清理
4. 历史报告和备份按审计价值保留

## 未来模块

可能的 display-only 模块：

- Candidate Lifecycle
- Post-trade Plan
- Entry Setup
- Risk / Reward view
- Validator History
- Source Trace Drilldown

可能的事件层：

- FDA / PDUFA
- IPO
- Investor Day
- Product Launch
- M&A
- Buyback
- Stock split
- News headline parser

## Phase 3c 期间不计划做

- 切换 active mode
- 替换 production validator
- 让 Validator v2 影响 clean-day 计数
- 降低 runtime P0/P1 要求
- 暴露敏感生产日志
- 增加自动化生产动作
