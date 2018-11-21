# DOM增删改查


### jquery获取子节点，父节点 ，兄弟节点 的方法
基本过滤器
- a) “:first”，选取第一个元素，别忘记它也是被放在一个集合里哦！因为JQuery它是DOM对象的一个集合。如，“$("tr:first")”返回所有tr元素的第一个tr元素，它仍然被保存在集合中。
- b) “:last”，选取最后一个元素。如:“$("tr:last")”返回所有tr元素的最后一个tr元素，它仍然被保存在集合中。


子元素过滤选择器

- a) “:nth-child(index/even/odd)”，选取索引为index的元素、索引为偶数的元素、索引为奇数的元素。
l nth-child(even/odd)：能选取每个父元素下的索引值为偶(奇)数的元素。
l nth-child(2)：能选取每个父元素下的索引值为 2 的元素。
l nth-child(3n)：能选取每个父元素下的索引值是 3 的倍数的元素。
l nth-child(3n + 1)：能选取每个父元素下的索引值是 3n + 1的元素。
- b) “:first-child”，选取第一个子元素。
- c) “:last-child”，选取最后一个子元素。
- d) “:only-child”，选取唯一子元素，它的父元素只有它这一个子元素。

获取子父兄弟的例子：
```html
<ul class="par">
<li id="firstli">
<h3 class="title">条目一</h3>
<ul class="par">
<li id="dwtedx">第一项</li>
<li>第二项</li>
</ul>
</li>
</ul>
```

子节点：
```javascript
$(".par:first-child");//取得id为firstli的节点
$('#firstli h3.title');//取得条目一的h3
$("#firstli").find("h3");//找到子兄弟节点h3
$("#firstli").children("h3.title");//取得子节点h3、class为title
```
父节点：
```javascript
$("#dwtedx").parent().parent();//取得id为firstli的li节点
$("#dwtedx").parent().parent(".par");//取得最上面的ul节点
$("#dwtedx").parent(".par");//取得向上第一层的ul节点 以上是通过parent的方式来获取父节点的
```
兄弟节点：
```javascript
$(".title").parent().find('ul');//找到自己的兄弟节点ul 就是通过先找到 h3 与 ul 共同的父节点 li 然后来用 find() 找到 ul
$(".title").siblings('ul');//找到自己的兄弟节点ul
```


### jquery增删查改：增加删除获取设置
##### 增加：
- append() - 在被选元素的结尾插入内容
- prepend() - 在被选元素的开头插入内容
- after() - 在被选元素之后插入内容
- before() - 在被选元素之前插入内容
- appendTo() - 把所有匹配的元素追加到指定的元素元素集合中，例如：$("<b>Hello World!</b>").appendTo("p");


##### 删除：
- remove() - 删除被选元素（及其子元素），例如：（过滤被删除的元素）$("p").remove(".italic");
- empty() - 从被选元素中删除子元素，例如：$("#div1").empty();


##### 获取：

获得内容 - text()、html() 以及 val()

- text() - 设置或返回所选元素的文本内容
- html() - 设置或返回所选元素的内容（包括 HTML 标记）
- val() - 设置或返回表单字段的值

获取属性 - attr()
- jQuery attr() 方法用于获取属性值$("#w3s").attr("href")

##### 设置：
设置内容 - text()、html() 以及 val()
- text() - 设置或返回所选元素的文本内容：$("#test1").text("Hello world!");
- html() - 设置或返回所选元素的内容（包括 HTML 标记）：$("#test2").html("<b>Hello world!</b>");
- val() - 设置或返回表单字段的值：$("#test3").val("Dolly Duck");
设置属性 - attr()
jQuery attr() 方法也用于设置/改变属性值。
attr设置多个值
```javascript
$("#w3s").attr({
  "href" : "http://www.w3school.com.cn/jquery",
  "title" : "W3School jQuery Tutorial"
});
```

