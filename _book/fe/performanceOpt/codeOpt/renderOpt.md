# 渲染优化

- HTML使用Viewport
- 减少DOM节点
- 尽里使用CSS3动画，硬件加速
- 合理使requestAnimationFrame动画代替 setTimeout
- 适当使用Canvas动画
- Touchmove、Scroll事件会导致多次渲染
- 使用（CSS3 transitions、CSS3 3D、transforms、Opacity、Canvas、WebGL、Video )来触发GPU渲染，硬件加速机制