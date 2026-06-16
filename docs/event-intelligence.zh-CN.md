# Event Intelligence 事件情报

Event Intelligence 是 Prism 的事件上下文展示层。

它帮助用户理解某个对象或板块为什么值得关注，但不会直接改变生产判断逻辑。

## 当前事件层

Prism 当前记录和展示：

- 财报事件
- SEC 与事件风险
- 板块上下文
- ETF flow 上下文

## Display-only 规则

Event Intelligence 当前只用于展示。

它不会：

- 修改生产评分
- 修改 Phase 3c 验证标准
- 修改 Recommendation 生产逻辑
- 将 research-only 对象提升为正式动作

## 财报

财报层用于展示已知的近期或即将到来的财报时间。

例如：

- 今日盘前
- 今日盘后
- 距离财报还有若干天
- 暂无近期财报信息

## SEC 与事件风险

SEC 层用于展示文件或事件风险提示。

这些内容只作为上下文，不作为自动规则。

## 板块与 ETF 上下文

板块和 ETF 信息可以帮助理解更大的市场环境。

它们用于解释，不直接进入生产 gate。

## 未来候选事件层

未来可能补充：

- FDA / PDUFA
- IPO
- Investor Day
- Product Launch
- M&A
- Buyback
- Stock split
- News headline parser

这些内容会在验证与可观测性稳定后再考虑。
