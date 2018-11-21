# Web Sockets 以及 服务器推事件

## Web Sockets

WebSocket 是 HTML5 一种新的协议。它实现了浏览器与服务器全双工通信，能更好的节省服务器资源和带宽并达到实时通讯，它建立在 TCP 之上，同 HTTP 一样通过 TCP 来传输数据，但是它和 HTTP 最大不同是：


- WebSocket 是一种双向通信协议，在建立连接后，WebSocket 服务器和 Browser/Client Agent 都能主动的向对方发送或接收数据，就像 Socket 一样；

- WebSocket 需要类似 TCP 的客户端和服务器端通过握手连接，连接成功后才能相互通信。


## Server-sent events

允许服务器向客户端推送事件，而不是仅在响应客户端请求时服务器才能发送数据的传统范式。



参考：


[Web Sockets](https://www.ibm.com/developerworks/cn/java/j-lo-WebSocket/index.html)


[WebSockets_API](https://developer.mozilla.org/zh-CN/docs/Web/API/WebSockets_API)


[Server-sent events](https://developer.mozilla.org/zh-CN/docs/Server-sent_events/Using_server-sent_events)

[HTML5 服务器推送事件（Server-sent Events）实战开发](https://www.ibm.com/developerworks/cn/web/1307_chengfu_serversentevent/index.html)