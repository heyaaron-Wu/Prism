# Decision Card 决策解释卡

Decision Card 是 Prism 的解释层，用于说明持仓上下文、候选对象上下文、research-only 对象、news-only 对象和事件驱动上下文。

它的目标是帮助人工复核者理解对象为什么出现、有哪些上下文、有哪些限制，以及该信息是仅供复核、仅供研究、仅供验证，还是可能在独立人工复核后进入更强的判断范围。

## 目的

Decision Card 用结构化方式回答：

- 对象为什么出现，
- 属于哪一种上下文类别，
- 有哪些 blocker 或限制条件，
- 是否存在相关事件情报，
- 当前是 informational、research-only、shadow-only，还是更强复核范围的一部分，
- 支撑数据中有哪些缺失或过期风险。

## 范围分离

Prism 会明确区分不同范围：

```text
REAL_CONTEXT       真实账户或真实持仓复核上下文
VIRTUAL_CONTEXT    虚拟或 paper 账户复核上下文
SHADOW_CONTEXT     仅用于验证的候选上下文
RESEARCH_ONLY      仅用于研究观察
NEWS_ONLY          新闻或事件上下文
DISCOVERED         已发现但未提升为更强状态的对象
```

公开示例使用泛化标签，不使用真实标的或账户特定对象：

```text
EXAMPLE_REAL_CONTEXT
EXAMPLE_VIRTUAL_CONTEXT
EXAMPLE_SHADOW_CANDIDATE
EXAMPLE_RESEARCH_ONLY
EXAMPLE_NEWS_ONLY
```

这样文档会聚焦系统设计，而不是暴露私有运行状态。

## 常见卡片区块

Decision Card 可以包含：

1. 基础身份
2. 范围分类
3. 为什么出现
4. 来源追踪与新鲜度
5. 事件情报信息
6. blocker、限制条件或等待原因
7. 复核备注
8. 风险上下文占位
9. 复核后管理占位
10. 安全边界

不是每张卡片都必须包含全部区块。目标是把已有上下文说清楚，并避免在证据缺失时制造确定性。

## Summary 与 Detail 模式

Decision Card 可以用不同粒度展示：

| 模式 | 作用 |
| --- | --- |
| Summary | 用于快速浏览多个对象的短视图。 |
| Full | 用于复核的更完整解释 payload。 |
| Detail drawer | 展开查看来源、事件、blocker 和安全边界上下文。 |

## 事件情报接入

Event Intelligence 可以提供 display-only 上下文，例如：

- 财报时间，
- 披露或事件上下文，
- 板块级上下文，
- ETF flow 上下文，
- 其他延期加入的事件类型。

这些信息有助于解释为什么某个对象需要关注，但不会自动生成 actionability。

## 安全边界

Decision Card 是解释与展示工具。

它不会：

- 执行交易，
- 修改策略参数，
- 替代验证逻辑，
- 影响 validation-day 计数，
- 把 display-only 事件情报提升为 production gate，
- 取消独立人工复核的必要性。

## 公开范围边界

本文刻意不公开：

- 真实账户持仓，
- 私有 watchlist 对象，
- 账户特定标的，
- 券商特定订单行为，
- 原始 runtime payload，
- 私有 decision log，
- 生产执行内部逻辑。

本文的作用是记录解释层设计，而不是暴露运行状态。
