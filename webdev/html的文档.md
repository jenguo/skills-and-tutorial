# html的文档
---

## css 

### css position 属性

* static
  - 元素框正常生成. 块级元素生成一个矩形框, 作为文档流的一部分, 行内元素则会创建一个或多行框, 置于父元素中.
* relative:
  - 元素框偏移某个距离. 元素扔保持其未定位前的形状, 它原本所占有的空间扔保留

* absolute:
  * 元素框从文档流完全删除, 并相对于其包含块定位. 包含快定位可能是文档中的另一个元素或是初始包含块. 元素原先在正常文档流中所占的空间会关闭, 就好像原来的不存在一样. 元素定位生成一个块级框, 而不论原来他在正常流中生成合众类型框

* fixed:
  * 元素框的表现类似于将position 设置为 absolute, 不过其包含块的是视窗本身.
