## inline-block中不对齐的问题

首先解决两个inline-block元素不对齐的问题，原因是元素的vertical-align默认值为base-line，也就是基线对齐，因此只要将其设置为top就能解决；

关于基线问题，[移步这里](/基线.md)。

##块盒间空隙问题

再者，注意到另一个问题，就是不同浏览器inline-block会产生间距空袭值，且间距值不同。

测试下chrome，ie9间距约为4px,firefox约为8px。

解决方法当然可以写负margin，不过这里有更好的解决方法。

————————————

HTML 中的换行符、空格符、制表符等产生了空白符，而这些归根结底都是字符，那么它们的大小都是 受 font-size 来控制的，字体大小直接导致 inline 或者 inline-block 后元素之间空隙的大小，把 inline-block 元素间的空隙认为总是某个固定大小是错误的。

————————————

那是否在父容器设置font-size:0;就行了？非也，letter-spacing作为字间距也是会影响到，因此为了兼容需要把字间距设为复制，opera和safari的间距值最大，有-5px,因此以最大的兼容，加上letter-spacing:-5px;

低版本的 chrome 浏览器为了不让文字过小不利于阅读，默认是不支持 font-size:0 的，还好我们有 -webkit-text-size-adjust 这个私有属性来控制，当设为 none 时就支持字体大小为 0 了

然而，在IE6，7还是会出现1px的间隙。解决办法：为IE添加*word-spacing:-1px;/* IE6、7 */就可以了。

最后记得把样式重置回来。

##IE6 IE7下行内元素与块元素inline-block的差异

对于行内元素，直接设置inline-block，可以表现的与现代浏览器类似；对于块元素，需要在inline-block后设置display:inline
