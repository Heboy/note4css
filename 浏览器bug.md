bug总结
---

- IE7负边距隐藏

	当应用负边距导致元素超出父框时会被隐藏，解决方案：
		
		为隐藏元素添加如下样式

		*zoom:1;
    	_position:relative;

- IE7之前不支持min-height,max-height以及相关height属性
- IE7不支持display:inline-block，解决办法：

		display: inline-block;
    	*display:inline;
    	*zoom:1;
让ie6/7识别display:inline;来覆盖上面的display:inline-block;然后通过zoom:1;来触发haslayout让inline元素在ie中表现得和inline-block元素一样。

- IE7下float:right换行bug，需要将float:right的元素放在非float元素前面
- IE9以下都不支持placeholder
