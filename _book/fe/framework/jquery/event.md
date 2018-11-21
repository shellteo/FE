# 事件处理

![zx](http://img.mukewang.com/54c89def0001c19105810528.jpg)
Query对每一个elem中的每一种事件，只会绑定一次事件处理函数（绑定这个elemData.handle）,
而这个elemData.handle实际只做一件事，就是把event丢到jQuery内部的事件分发程序
```javascript
jQuery.event.dispatch.apply( eventHandle.elem, arguments );
```
而不同的事件绑定，具体是由jQuery内部维护的事件列队来区分（就是那个elemData.events）
在elemData中获取到events和handle之后，接下来就需要知道这次绑定的是什么事件了
jquery如何实现多事件绑定同一个函数：
多事件处理：
如果是多事件分组的情况jQuery(...).bind("mouseover mouseout", fn);
事件可能是通过空格键分隔的字符串，所以将其变成字符串数组
而传入的回调函数会以数组的方式缓存起来
jquery的handle函数都是缓存在elemData中
elemData中 有两个重要的属性，
一个是events，是jQuery内部维护的事件列队
一个是handle，是实际绑定到elem中的事件处理函数