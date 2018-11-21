# DOM对象

## js获取子节点、父节点、兄弟节点

```javascript
var s= document.getElementById("par");
```

- 子节点:

```javascript
元素树：
var chils= s.children; //得到s的全部子元素节点
var fc=s.firstElementChild; //获得s的第一个子节点
var lc=s.lastElementChild; //获得s的最后一个子节点
节点树：
var chils= s.childNodes; //得到s的全部子节点
var fc=s.firstChild; //获得s的第一个子节点
var lc=s.lastChild; //获得s的最后一个子节点
```

- 父节点:

```javascript
元素树：
var par=s.parentElement; //得到s的父节点
节点树：
var par=s.parentNode; //得到s的父节点
```

- 兄弟节点

```javascript
元素树
var ns=s.nextElementSibling; //获得s的下一个兄弟节点
var ps=s.previousElementSibling; //得到s的上一个兄弟节点
节点树：
var ns=s.nextSibling; //获得s的下一个兄弟节点
var ps=s.previousSibling; //得到s的上一个兄弟节点
```


## js节点增删查改

### appendChild()
通过把一个节点增加到当前节点的childNodes[]组，给文档树增加节点。返回值为新增加的节点。


如果传入到 appendChild()中的节点已经是文档的一部分了，那结果就是将该节点从原来的位置转移到新位置。

```javascript
var returnedNode = someNode.appendChild(newNode);
```

### insertBefore()
给文档树插入一个节点，位置在当前节点的指定子节点之前。如果该节点已经存在，则删除之再插入到它的位置。

```javascript
//插入后成为最后一个子节点
returnedNode = someNode.insertBefore(newNode, null);
alert(newNode == someNode.lastChild); //true
//插入后成为第一个子节点
var returnedNode = someNode.insertBefore(newNode, someNode.firstChild);
alert(returnedNode == newNode); //true
alert(newNode == someNode.firstChild); //true
//插入到最后一个子节点前面
returnedNode = someNode.insertBefore(newNode, someNode.lastChild);
alert(newNode == someNode.childNodes[someNode.childNodes.length-2]); //true
```

### removeChild()

从文档树中删除并返回指定的子节点。
```javascript
//移除第一个子节点
var formerFirstChild = someNode.removeChild(someNode.firstChild);
//移除最后一个子节点
var formerLastChild = someNode.removeChild(someNode.lastChild);
replaceChild()
从文档树中删除并返回指定的子节点，用另一个节点替换它。
//替换第一个子节点
var returnedNode = someNode.replaceChild(newNode, someNode.firstChild);
//替换最后一个子节点
returnedNode = someNode.replaceChild(newNode, someNode.lastChild);
```

### cloneNode()

复制当前节点，或者复制当前节点以及它的所有子孙节点。


### hasChildNodes()

如果当前节点拥有子节点，则将返回true。


## js获取select选中的值
  - 1:拿到select对象： var myselect=document.getElementById("test");
  - 2：拿到选中项的索引：var index=myselect.selectedIndex ; // selectedIndex代表的是你所选中项的index
  - 3:拿到选中项options的value： myselect.options[index].value;
  - 4:拿到选中项options的text： myselect.options[index].text;

获取checkbox选中的值
```html
<label for="nan">男</label>
<input type="checkbox" id="nan" value="男" name="sex">
<label for="nv">女</label>
<input type="checkbox" id="nv" value="女" name="sex">
<script>
var ck= document.getElementsByName("sex");
for (var i = 0; i < ck.length; i++) {
  if(ck[i].checked){
  console.log(ck[i].value);
  }
}
</script>
```

## 节点树和元素树


节点树：遍历DOM树中的节点，包含元素节点之外的其他节点，如注释节点、文字节点（包括之间的空格）等


属性有：parentNode，childNodes，firstChild，lastChild，nextSibling，previousSibling

![节点树](https://myblog-images1.oss-cn-beijing.aliyuncs.com/images/js-guide/05.png)

元素树：遍历DOM树中的元素（element）节点，而不包含元素节点之外的其他节点，如注释节点、文字节点（包括之间的空格） 等属性有如下：
![元素树](https://myblog-images1.oss-cn-beijing.aliyuncs.com/images/js-guide/06.png)


代码解释
```html
<div id="container">    
	这里是文字节点。    
	<br/>    
	<!-- 这里是注释文字 -->    
	<div>这个是真正的节点。</div>    
	<mxh>自定义标签被认可吗？</mxh>
</div>
<script>
	window.onload  = function () {
	    var container = document.getElementById("container");
	    console.log(container.childNodes);
	    console.log(container.children);
	}
</script>
```
运行结果
![demo](https://myblog-images1.oss-cn-beijing.aliyuncs.com/images/js-guide/07.png)
