# select 模块
--- 

网络通信被Unix系统抽象为文件的读写，通常是一个设备，由设备驱动程序提供，驱动可以知道自身的数据是否可用。支持阻塞操作的设备驱动通常会实现一组自身的等待队列，如读/写等待队列用于支持上层(用户层)所需的block或non-block操作。设备的文件的资源如果可用（可读或者可写）则会通知进程，反之则会让进程睡眠，等到数据到来可用的时候，再唤醒进程。

这些设备的文件描述符被放在一个数组中，然后select调用的时候遍历这个数组，如果对于的文件描述符可读则会返回改文件描述符。当遍历结束之后，如果仍然没有一个可用设备文件描述符，select让用户进程则会睡眠，直到等待资源可用的时候在唤醒，遍历之前那个监视的数组。每次遍历都是线性的

文／人世间（简书作者）
原文链接：http://www.jianshu.com/p/edb9ddd51c3d
著作权归作者所有，转载请联系作者获得授权，并标注“简书作者”。
