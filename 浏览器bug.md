bug总结
---

- IE7负边距隐藏

	当应用负边距导致元素超出父框时会被隐藏，解决方案：
		
		为隐藏元素什么如下样式

		*zoom:1;
    	_position:relative;