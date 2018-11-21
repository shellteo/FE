# virtual-dom

### 几个步骤
- 用 JavaScript 对象结构表示 DOM 树的结构；然后用这个树构建一个真正的 DOM 树，插到文档当中
- 当状态变更的时候，重新构造一棵新的对象树。然后用新的树和旧的树进行比较，记录两棵树差异（diff）
- 把2所记录的差异应用到步骤1所构建的真正的DOM树上，视图就更新了
Virtual DOM 本质上就是在 JS 和 DOM 之间做了一个缓存。可以类比 CPU 和硬盘，既然硬盘这么慢，我们就在它们之间加个缓存：既然 DOM 这么慢，我们就在它们 JS 和 DOM 之间加个缓存。CPU（JS）只操作内存（Virtual DOM），最后的时候再把变更写入硬盘（DOM）。


过程：先做diff得到Patch，patch在应用到DOM上，假设在任意时候有，VirtualDom1 == DOM1 （组织结构相同）。当有新数据来的时候，我生成VirtualDom2，然后去和VirtualDom1做diff，得到一个Patch。然后将这个Patch去应用到DOM1上，得到DOM2。
如果一切正常，那么有VirtualDom2 == DOM2。