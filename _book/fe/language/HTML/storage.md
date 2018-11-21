# 离线 & 存储

localStorage和sessionStorage用法相同：如下（同样适用于sessionStorage）


## 设置值

```javascript
localStorage.a = 3;//设置a为"3"
localStorage["a"] = "sfsf";//设置a为"sfsf"，覆盖上面的值
localStorage.setItem("b","isaac");//设置b为"isaac"
```


## 获取值
注意：获取到的值都是字符串，使用的时候需要解析

```javascript
var a1 = localStorage["a"];//获取a的值
var a2 = localStorage.a;//获取a的值
var b = localStorage.getItem("b");//获取b的值
```


## 清除值

```javascript
localStorage.removeItem("c");//清除c的值
localStorage.clear();//全部删除
```


## 有效期和作用域
**cookie有效期**：cookie默认有效期非常短暂，存在于web浏览器会话期间，当浏览器关闭，cookie也就消失了。如果要延长cookie的有效期，可以设置max-age属性（单位秒）


**cookie作用域**：cookie作用域是通过domain文档源和path文档路径来确定的。默认情况下，cookie和创建它的web页面有关，并对web页面和该web页面同目录或者子目录的其他web页面可见。当设置path="/"，它的作用域就变成文档源级别的了。


**localStorage有效期**：永不失效，除非web应用主动删除。


**localStorage作用域**：localStorage的作用域是限定在文档源级别的。文档源通过协议、主机名以及端口三者来确定。


**sessionStorage有效期**：sessionStorage的有效期是和存储数据脚本所在的最顶层的窗口或者是浏览器标签是一样的，一旦窗口或者标签页被永久关闭了，存储的数据也就失效了。


**sessionStorage作用域**：sessionStorage的作用域也是限定在文档源级别。但需要注意的是，如果相同文档源的页面渲染在不同的标签中，sessionStorage的数据是无法共享的。


- **存储大小区别：**


除了上述列举的，cookie和localStorage、sessionStorage在存储大小的限制也不一样， 由于每个浏览器的实现标准都不一样，只说一下RFC 2965推荐标准（浏览器保存cookie不超过300个，为每个服务器保存的cookie不超过20个，每个cookie大小不超过4KB）。localStorage、sessionStorage设置值时可以达到8M.