# 关于c语言整形变量的规则

tag:**`gcc`  `integer`  `附属关键词`**

###  三种用于修饰整型变量的附属关键词

##### 	short

``` short int ```

占用空间小。

有符号类型。

##### int

you know

##### 	long

`long int`

占用空间大于等于int

`long long int [或 long long(C90)]`

这种形式最少占用64位。

##### unsigned 

所有的整形声明前都可以加`unsigned`,这个修饰词将原本对称的**(-a,+a)**区间变为了**(0,2a)**

`unsigned int ` 

`unsigned short int`

`unsigned long int`

`unsigned long long int (C90)`

### 三种变量之间的大小关系

一般而言，常见的PC配置是：

* `long long`型占了64位，即是8**Bytes**

* `long`型占了32位，即是4**Bytes**

* `int`型占了16或32位

  一般来说，为了表示一个正整数，有以下方法
  $$
  short < unsignedshort<int<unsigned int <long<unsignedlong <long long
  $$
  

### 打印这些类型时

##### 	打印八进制与十六进制

使用**`o`**与**`x`**来表示八进制与十六进制。

##### 	打印**unsigned** int型

使用 **`%u`** 来表示。

##### 	打印有`long`存在的类型

* 如果是`long`与`unsigned`相结合，则是**`%lu`**或者**`%llu`**，在u前加关键词l

* 如果是`long`与`int`相结合,则是**`%ld`**或者**`%lld`**

  

  

  

​	