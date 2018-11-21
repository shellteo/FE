# HTTP/HTTPs协议

### HTTP的特性

- HTTP构建于TCP/IP协议之上，默认端口号是80
- HTTP是无连接无状态的


### 请求报文

- 状态行
- 请求头
- 消息主体


### 响应报文：

- 状态行
- 响应头(Response Header)
- 响应正文


### 常见的状态码：

- 200 OK 客户端请求成功
- 301 Moved Permanently 请求永久重定向
- 302 Moved Temporarily 请求临时重定向
- 304 Not Modified 文件未修改，可以直接使用缓存的文件。
- 400 Bad Request 由于客户端请求有语法错误，不能被服务器所理解。
- 401 Unauthorized 请求未经授权。这个状态代码必须和WWW-Authenticate报头域一起使用
- 403 Forbidden 服务器收到请求，但是拒绝提供服务。服务器通常会在响应正文中给出不提供服务的原因
- 404 Not Found 请求的资源不存在，例如，输入了错误的URL
- 500 Internal Server Error 服务器发生不可预期的错误，导致无法完成客户端的请求。
- 503 Service Unavailable 服务器当前不能够处理客户端的请求，在一段时间之后，服务器可能会恢复正常。


### GET和POST请求

![zxplus](https://myblog-images1.oss-cn-beijing.aliyuncs.com/Image.png)

### request头部：
- If-Modified-Since
作用： 把浏览器端缓存页面的最后修改时间发送到服务器去，服务器会把这个时间与服务器上实际文件的最后修改时间进行对比。如果时间一致，那么返回304，客户端就直接使用本地缓存文件。如果时间不一致，就会返回200和新的文件内容。客户端接到之后，会丢弃旧文件，把新文件缓存起来，并显示在浏览器中.
- If-None-Match
作用: If-None-Match和ETag一起工作，工作原理是在HTTP Response中添加ETag信息。 当用户再次请求该资源时，将在HTTP Request 中加入If-None-Match信息(ETag的值)。如果服务器验证资源的ETag没有改变（该资源没有更新），将返回一个304状态告诉客户端使用本地缓存文件。否则将返回200状态和新的资源和Etag. 使用这样的机制将提高网站的性能
例如: If-None-Match: "03f2b33c0bfcc1:0"
### response头部：
- Expires
作用: 浏览器会在指定过期时间内使用本地缓存
例如: Expires: Tue, 08 Feb 2022 11:35:14 GMT
- ETag
作用: 和If-None-Match 配合使用。 （实例请看上节中If-None-Match的实例）
例如: ETag: "03f2b33c0bfcc1:0"
- Last-Modified:
作用： 用于指示资源的最后修改日期和时间。（实例请看上节的If-Modified-Since的实例）
例如: Last-Modified: Wed, 21 Dec 2011 09:09:10 GMT