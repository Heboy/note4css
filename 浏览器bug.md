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

- border:0与border:none
		
		{
			border:none;
			border:0;
		}
IE7只能通过0来实现无边框效果，现代浏览器可以通过上述两种方案实现，但是0比none多渲染一个border-width:0，所以一般通过none来实现无边框


- IE7局部滚动区域下绝对定位或相对定位元素不随滚动条滚动的bug，为滚动区域添加如下样式：
		
		*position:relative;
		*left:0;
		*top:0;