# 非关系型数据库

Redis、memcached、MongoDB

### redis的原理
- redis的ae事件处理
- redis是单线程，memcached是多线程的
- redis快的原因：redis用自己实现的事件分离器，代码量很短，没有cas，没有lock，epoll
- redis如何实现io多路复用技术的：epoll，包含三个方法：epoll给我们提供了3个api： epoll_create, - epoll_ctl, epoll_wait


epoll相对于其他io多路复用技术（select，poll）的优势：
1. epoll 没有最大并发连接的限制，上限是最大可以打开文件的数目，这个数字一般远大于 2048, 一般来说这个数目和系统内存关系很大 ，具体数目可以 cat /proc/sys/fs/file-max 察看。
2. 效率提升， Epoll 最大的优点就在于它只管你“活跃”的连接 ，而跟连接总数无关，因此在实际的网络环境中， Epoll 的效率就会远远高于 select 和 poll 。
3. 内存拷贝， Epoll 在这点上使用了“共享内存 ”，这个内存拷贝也省略了。