# 异步
Callback、generator（yield && co）、async/await、Promise（promise.race、promise.all、Promise库：q、bluebird）


js延迟加载的方式有哪些？


defer和async、动态创建DOM方式（用得最多）、按需异步载入js
defer，只支持IE，dom结构解析完（标签 + 样式（内容不一定下载完））才异步执行

```javascript
<script type="text/javascript" defer="defer">
alert(document.getElementById("p1").firstChild.nodeValue);
</script>
sync 属性仅适用于外部脚本（只有在使用 src 属性时）加载完毕后立刻异步执行，IE8及以下不兼容
<script type="text/javascript" src="demo_async.js" async="async"></script>
动态创建DOM方式（用得最多）
<script type="text/javascript">
function downloadJSAtOnload() {
var element = document.createElement("script");
element.src = "defer.js";
document.body.appendChild(element);
}
if (window.addEventListener)
     window.addEventListener("load", downloadJSAtOnload, false);
else if (window.attachEvent)
     window.attachEvent("onload", downloadJSAtOnload);
else window.onload = downloadJSAtOnload;
</script>
```