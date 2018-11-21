# History API

DOM window 对象通过 `history` 对象提供了对浏览器历史的访问。它暴露了很多有用的方法和属性，允许你在用户浏览历史中向前和向后跳转，同时——从HTML5开始——提供了对history栈中内容的操作。


HTML5引入了 `history.pushState()`和 `history.replaceState()` 方法，它们分别可以添加和修改历史记录条目。这些方法通常与`window.onpopstate` 配合使用。


参考： [history](https://developer.mozilla.org/zh-CN/docs/Web/API/History_API)