# Web Workers


Web Worker为Web内容在后台线程中运行脚本提供了一种简单的方法。线程可以执行任务而不干扰用户界面。


Web workers可分为两种类型：专用线程dedicated web worker，以及共享线程shared web worker。


Dedicated web worker随当前页面的关闭而结束；这意味着Dedicated web worker只能被创建它的页面访问。与之相对应的Shared web worker可以被多个页面访问。在Javascript代码中，“Work”类型代表Dedicated web worker，而“SharedWorker”类型代表Shared web worker。



参考：


[Web Workers](https://developer.mozilla.org/zh-CN/docs/Web/API/Web_Workers_API/Using_web_workers)