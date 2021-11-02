# select、poll、epoll - IO模型超详解

[参考](https://blog.csdn.net/XueyinGuo/article/details/113096163)

## Linux操作系统有关的IO知识铺垫

## PageCache

Linux内核所使用的的主要磁盘高速缓存。内核读写磁盘的时候都要用到这个`PageCache`。如果程序想要读的部分不在高速缓存，则先申请一个4KB大小的新页框加到`PageCache`，然后再用磁盘读到的数据填充。

写操作的时候，先把要写的数据写到`pageCache`，标记当前页面为脏，然后要么程序自己调用系统调用刷盘，要么就等着内核到了自己的默认设置去给你刷回去。

如果没有及时写出现了断电，那么你就白写了。

