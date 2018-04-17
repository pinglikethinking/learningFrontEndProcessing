## 常用布局

1. 传统布局：依赖float,position,margin等属性的布局

2. flex 布局：依赖 css3 属性 display:flex;建立起来的弹性盒子模型布局

3. grid 布局：依赖 width 百分比 和 媒体查询 实现自适应的 栅格布局

BFC：内部元素再怎么翻江倒海，都不会影响外部元素
触发形成 BFC 的情况如下：
- float:非none
- overflow:auto/scroll/hidden
- display:inline-block/table-cell/table-caption
- position:非relative/非static