# css

Cascading Style Sheets，层叠样式表，是一种 样式表 语言，用来描述 HTML 或 XML 文档的呈现。

## 常用布局

传统布局：依赖float,position,margin等属性的布局

flex 布局：依赖 css3 属性 display:flex;建立起来的弹性盒子模型布局

grid 布局：依赖 width 百分比 和 媒体查询 实现自适应的 栅格布局

BFC：内部元素再怎么翻江倒海，都不会影响外部元素
触发形成 BFC 的情况如下：
- float:非none
- overflow:auto/scroll/hidden
- display:inline-block/table-cell/table-caption
- position:非relative/非static

## 盒模型

box-sizing: content-box/padding-box/border-box/margin-box

常用的两种：

- content-box：width 就是设置的 width 既内容的宽度
- border-box：width = contentWidth + padding-left + border-left + padding-right + border-right

## 选择器权重计算

选择器进行分类：

- 内联样式
- ID 选择器
- class选择器，伪类，属性选择器
- 标签选择器，伪元素
- 通配符选择器 *

权重值从上而下依次是：1000，100，10，1，0

## position的理解

- static：处于文档流中，设置 top/bottom/left/right/z-index 无效

- relative：脱离文档流，设置left/top等时会相对原来位置移动，并保留原位置在文档流中，position:relative;对table-*无效

- absolute：脱离文档流，相对于最近的非static的父元素绝对定位，如果没有则相对根元素绝对定位。绝对定位的元素可以设置外边距，并且不会产生外边距合并问题

- fixed：脱离文档流，相对于屏幕视口（viewport）固定定位。当其父元素的transform非none时，相对于父元素固定定位，因为其创建了新的层叠上下文，父元素tansform后会归为同一层

- sticky：处于文档流中，对table-*无效。粘性定位是相对定位和固定定位的混合。元素在跨越特定阈值前为相对定位，之后为固定定位

```
  #one { position: sticky; top: 10px; }
  //在 viewport 视口滚动到元素 top 距离小于 10px 时，元素为固定定位，元素将固定在与顶部距离 10px 的位置，直到 viewport 视口回滚到大于阈值时。
  // 粘性定位常用于定位字母列表的头部元素
```

## 单位 px,em,rem,vw,vh,vmin,vmax,%

单位与输出媒体有关(除此之外，还有，绝对单位 (cm, mm, in, pt and pc)，不推荐使用)，如下：

- px：屏幕像素

- em：字体大小

- ex：小写字母高度

- rem：rem(em的"根(root)")是文件的根元素的字体大小

- vw：视窗的100分之1的宽度

- vh：视窗的100分之1的高度

- vmin: vw以及 vh间较小的那一方

- v-max: vw以及 vh间较大的那一方

- %：父元素宽度的百分比

## 水平垂直居中

- 文本类元素的水平居中：text-align:center
- 文本类元素的垂直居中：line-height 和 height 相等，当然是对于display:block/inline-block;

- 水平居中：margin：0 auto;
- 垂直居中：传统的方案（position + transform）;flex布局方案（display:flex;justify-content: center;align-items: center;）align-items: center;为垂直方向的对齐方式

## 实现正方形

width/height或者padding占位 单位统一用 vw 或者 %

## transform:translateZ 是什么

transform和opacity保证了元素属性的变化不影响文档流、也不受文档流影响；并且不会造成repaint

[点击查看一篇好文章](https://segmentfault.com/a/1190000008015671#articleHeader10)
