# 流畅的Python2015阅读
---


`__getitems__` 实现了对`[]`的处理

`__repr__`: 返回对象时, 可以用于人类语言描述
`__str__`: 是在打印时, 用于人类语言描述.(没有实现`__str__`, 会使用`__repr__`)
前者方便我们调试和
记录日志， 

## 第二部分 数据结构

filter
map


nametuple

-fields
_make()
_asdict() --> collections.OrderedDict

省略的正确写法是三个英文句号, 省略在Python解析器眼里是一个符号, 实际上是Ellipsis对象的别名, 而Ellpsis对象又是ellipsius类的单一实例, 可以在用在函数的参数清单中: f(a,...,z) a[i:...]

笛卡尔积(矩阵的乘法):


切片的赋值



```
>>> t = (1, 2, [30, 40])
>>> t[2] += [50, 60]
>>> 

```
到底会发生下面 4 种情况中的哪一种？

a. t 变成 (1, 2, [30, 40, 50, 60])。
b. 因为 tuple 不支持对它的元素赋值， 所以会抛出 TypeError 异常。
c. 以上两个都不是。
d. a 和 b 都是对的

我刚看到这个问题的时候， 异常确定地选择了 b， 但其实答案是 d， 也
就是说 a 和 b 都是对的！ 示例 2-15 是运行这段代码得到的结果， 用的
Python 版本是 3.4， 但是在 2.7 中结果也一样。

有读者提出， 如果写成 t[2].extend([50, 60]) 就能避免这个异常。 确实是这样， 但这个
例子是为了展示这种奇怪的现象而专门写的。

* 

