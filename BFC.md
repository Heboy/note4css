##Box、Formatting Context
###Box
Box 是 CSS 布局的对象和基本单位， 直观点来说，就是一个页面是由很多个 Box 组成的。元素的类型和 display 属性，决定了这个 Box 的类型。 不同类型的 Box， 会参与不同的 Formatting Context（一个决定如何渲染文档的容器），因此Box内的元素会以不同的方式渲染。让我们看看有哪些盒子：

- block-level box：display 属性为 block, list-item, table 的元素，会生成 block-level box。并且参与 block fomatting context；([Values of the 'display' property that make an element block-level include: 'block', 'list-item', and 'table'. Block-level boxes are boxes that participate in a block formatting context.](http://http://dev.w3.org/csswg/css2/visuren.html#block-level))

- inline-level box：display 属性为 inline, inline-block, inline-table 的元素，会生成 inline-level box。并且参与 inline formatting context；

###block-level box
block-level box指那些参与block formatting context的box。
block-level box通常也是block container box，除非它是table box或者替换元素的box。

###Formatting context
Formatting context 是 W3C CSS2.1 规范中的一个概念。它是页面中的一块渲染区域，并且有一套渲染规则，它决定了其子元素将如何定位，以及和其他元素的关系和相互作用。最常见的 Formatting context 有 Block fomatting context (简称BFC)和 Inline formatting context (简称IFC)。

##BFC
BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干。

###触发BFC的规则
浮动，绝对定位元素，不是block box的block container（inline-blocks，table-cells，table-captions），以及overflow!=visible的block box，会为他们的内容创建新的BFC

###BFC布局规则：

- Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
- BFC块不会与float box重叠
- BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素
- 计算BFC的高度时，BFC内部浮动元素也参与计算

###哪些元素会生成BFC?

- 根元素
- float属性不为none
- position为absolute或fixed
- display为inline-block, table-cell, table-caption, flex, inline-flex
- overflow不为visible