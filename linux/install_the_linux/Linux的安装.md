# Linux的安装

tag :   `linux`    ` 挂载 `

之前在安装的时候老是被挂载的问题一脸蒙逼，在这里记录一下**linux**的不同分区的用法以及挂载要求。

#### 先补一下磁盘的构成:

![磁盘结构](http://github.com/Focavn/linux_blogs/blob/master/install_the_linux/pic/磁盘结构.png)
/*注意到 在这个路径中%20代表了空格 在这里要注意名字一定要合法！否则真的很麻烦！

1. 磁盘的数据在盘片上，盘片上有扇区与柱面，一般磁盘有多个盘片（图中三层）

2. 绿色的部分称为**扇区**，是最小的储存单位，512bytes
3. 由扇区组成的一个圆环称为**磁道**
4. 垂直方向上的多条磁道（图中三个）组成的垂直环管称为**柱面**，是分割硬盘的最小单位。

#### 再说一下第一扇区的作用

整块磁盘的第一个扇区是最重要的，记录了两个主要信息

* 主引导分区 **446**bytes
* 分区表 **64** bytes

#### 磁盘的分区表

![partion table and function of disk](http://github.com/Focavn/linux_blogs/blob/master/install_the_linux/pic/partion_table_and_function_of_disk.png)

这个图中似乎是左边是圆心，右边是边缘，里边的长方形是第一条磁道的第一扇区。白色的是 `主引导分区MBR`，黑色的便是`分区表`。

**1 byte = 8 bits** 也就是共 $ 2^8 = 256 $ 个排列方式，即是256个二 0 ，1 。

由于某些我并看不懂的原因[^1]，每个分区在分区表的**64**个bytes中，由于每一个分区的大小一般为16bytes，所以对于一个磁盘，最多将柱面分成四份，即四个分区，称为主分区或拓展分区。
$$
主分区数 + 扩展分区数 \le 4 \\
扩展分区数 \equiv 1
扩展分区
$$
所以在**linux**中，一般磁盘的分区的设备文件名如下：

```
P1 : /dev/hda1
p1 : /dev/hda2
L1 : /dev/hda5
L2 : /dev/hda6
L3 : /dev/hda7
L4 : /dev/hda8
L5 : /dev/hda9
```

该例子中，**L**开头的逻辑分区从**hda5**开始，因为**1~4**保留给主分区。而从**hda2**开始意味着**hda2**被分成了**L1~L5**。

#### ==目录树与挂载==

如下图，从跟目录 **/ root** 开始像树一样伸展开，但应该如何把这种储存模式与磁盘上的储存空间相结合起来呢？

![目录树](http://github.com/Focavn/linux_blogs/blob/master/install_the_linux/pic/dirtree.gif)

##### 	







## 一些安装前的规划

#### 选择你的distribution

稳定性：`RedHat`   `CentOS` 

桌面界面更舒适，更爽 ：`ubuntu`






[^1]:https://blog.csdn.net/White_Idiot/article/details/80088115 
