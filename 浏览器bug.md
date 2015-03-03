bug总结
---

- IE7负边距隐藏

	当应用负边距导致元素超出父框时会被隐藏，解决方案：
		
		为隐藏元素什么如下样式

		*zoom:1;
    	_position:relative;

- IE7之前不支持min-height,max-height以及相关height属性
- IE7不支持display:inline-block，解决办法是声明inline-block后*display:inline
- IE9以下都不支持placeholder
