
`__getitem__`

`__len__`
`__repr__`

`__iter__`: 迭代相关

Iterble--> __iter__
Iterator --> __next__ __iter__


> 可迭代的对象一定不能是自身的迭代器. 也就是说, 可迭代的对象必须实现 `__iter__`方法,但是不能实现`__next__` 方法.  另一方面, 迭代器应该一直可以迭代. 迭代器的`__iter__`方法应该返回自身.


