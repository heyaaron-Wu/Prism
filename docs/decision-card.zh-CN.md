# Decision Card 决策解释卡

Decision Card 是 Prism 的解释层，用来帮助用户理解候选对象、研究对象、持仓上下文和事件上下文。

## 目的

Decision Card 用结构化方式回答：

- 为什么这个对象出现在系统中
- 当前属于什么状态
- 有哪些等待原因或限制条件
- 是否存在相关事件情报
- 是否只是信息展示

## 状态分层

Prism 会区分不同对象状态：

- REAL：真实上下文
- VIRTUAL：虚拟或 paper 上下文
- SHADOW：Shadow 验证候选
- RESEARCH_ONLY：研究对象
- NEWS_ONLY：新闻或事件对象
- DISCOVERED：已发现但未提升状态

## Detail Drawer

详情抽屉包含：

1. 基础身份
2. 为什么出现
3. 等待原因与限制条件
4. 入场设置占位
5. 风险收益占位
6. 后续管理占位
7. 安全边界
8. 事件情报信息

## 当前状态

已完成并验收：

- Backend v1.2
- summary / full mode
- Detail Drawer v1
- raw enum 汉化
- 缺字段安全显示
- 性能优化

## 边界

Decision Card 是解释与展示工具。

它不会：

- 修改策略参数
- 替代验证逻辑
- 影响 Phase 3c 计数
- 把 display-only 事件信息变成 gate
