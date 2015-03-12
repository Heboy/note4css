
##CSS2.1中的选择器
[点击这里](选择器.md)

##CSS3中的选择器
点击这里

##选择器优先级
[点击这里](选择器的优先级.md)

##可视化格式模型
###基本框
CSS假定每个元素都会生成一个或多个矩形框，包括内容区域，内边距，边框，外边距。这个假定的矩形框就是基本框。

###包含块
每个元素都相对其包含块摆放，可以说包含块就是一个元素的布局上下文，举个栗子：
	
	<div>
		<p>I m content</p>
	</div>
p的包含块就是div。

###display属性
- none	此元素不会被显示。
- block	此元素将显示为块级元素，此元素前后会带有换行符。
- inline	默认。此元素会被显示为内联元素，元素前后没有换行符。
- inline-block	行内块元素。（CSS2.1 新增的值）
- list-item	此元素会作为列表显示。
- run-in	此元素会根据上下文作为块级元素或内联元素显示。
- table	相关


###块级元素
[点击这里](块级元素的大小与边距.md)

###行内元素
[点击这里](行内元素的大小与边距.md)

##IE7的bug
[点击这里](浏览器bug.md)


##内联元素与inline-level boxes
内联元素是在一行内显示的，有些display属性可以设置元素为内联元素。

inline-level box指那些参与inline formatting context的box

##display对box的影响
- block

	让元素生成一个block box
- inline-block

	让元素生成inline-level block container
- inline

	让元素生成一个或多个inline box
- none

	不生成box，元素不显示
- table, inline-table, table-row-group, table-column, table-column-group, table-header-group, table-footer-group, table-row, table-cell, table-caption

	让元素表现的像table
