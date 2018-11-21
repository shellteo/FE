# 组件间通信

组件间通信

* 父组件向子组件通信: props

* 子组件向父组件通信: 回调函数/自定义事件

回调函数：


子类：
```html
<button onClick={this.props.hideConponent}>隐藏List3组件</button>
```
父类：
```html
<List3 hideConponent={this.hideConponent} />
```
* 跨级组件通信: 层层组件传递props/context
* 没有嵌套关系组件之间的通信: 自定义事件（类似nodejs发布订阅模式） ，可以使用库events或者react-broadcast


参考：https://juejin.im/post/5a2cbc57f265da431523d6de#comment

