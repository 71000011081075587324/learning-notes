## 自己操作中使用过的命令

#### 登录（root用户下）

```
# login
login：输入用户名
Password：输入口令su
```

<img src="Unix初级教程-随记/image-20210318200347011.png" alt="image-20210318200347011" style="zoom:80%;" />



#### 普通用户切换到root用户并关机

```linux
$ su -
输入root用户密码
# shutdown -h now
```

![image-20210318200302552](Unix初级教程-随记/image-20210318200302552.png)



#### root用户切换到已经登录的普通用户

```
# su - 普通用户名
```



## 第一章 绪论

### 微机

微型计算机称为微机，也称为个人计算机或PC。



### 基本硬件模块

<img src="Unix初级教程-随记/image-20210307180355219.png" alt="image-20210307180355219" style="zoom:80%;" />



### 处理器单元

处理器单元也称为中央处理单元或CPU，包含3个基本组成部分：

+ **算术逻辑单元（ALU）**

  <img src="Unix初级教程-随记/image-20210307180850648.png" alt="image-20210307180850648" style="zoom: 80%;" />

+ **寄存器**

  <img src="Unix初级教程-随记/image-20210307181222688.png" alt="image-20210307181222688" style="zoom: 80%;" />

+ **控制单元**

  <img src="Unix初级教程-随记/image-20210307183626309.png" alt="image-20210307183626309" style="zoom:80%;" />



### 内存

内存一般有两种：

+ **随记存储器（RAM）**

  <img src="Unix初级教程-随记/image-20210307183954549.png" alt="image-20210307183954549" style="zoom: 80%;" />

+ **只读存储器（ROM）**

  <img src="Unix初级教程-随记/image-20210307184105291.png" alt="image-20210307184105291" style="zoom:80%;" />



### 数据表示

<img src="Unix初级教程-随记/image-20210307184341893.png" alt="image-20210307184341893" style="zoom:67%;" />



### 性能指标

性能指标通常是针对每台计算机的组成部件、各部件间的通信能力和所有性能指标的综合测量。

+ **CPU速度**

  <img src="Unix初级教程-随记/image-20210307164731474.png" alt="image-20210307164731474" style="zoom:80%;" />

+ **访问时间**

  <img src="Unix初级教程-随记/image-20210307165010416.png" alt="image-20210307165010416" style="zoom:80%;" />

+ **通道速度**

  <img src="Unix初级教程-随记/image-20210307175038605.png" alt="image-20210307175038605" style="zoom:80%;" />

+ **总体性能指标**

  <img src="Unix初级教程-随记/image-20210307175119454.png" alt="image-20210307175119454" style="zoom:80%;" />



### 操作系统

操作系统的主要任务和功能

<img src="Unix初级教程-随记/image-20210307203616662.png" alt="image-20210307203616662" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210307213500115.png" alt="image-20210307213500115" style="zoom: 67%;" />

多核CPU可以最多“并行”处理和核数一样的进程，但其中的每个核任何时刻只有一个运行程序在占用它



#### 操作系统环境

介绍单任务、多任务、多用户、分时和批处理

<img src="Unix初级教程-随记/image-20210307220556091.png" alt="image-20210307220556091" style="zoom: 67%;" />

<img src="Unix初级教程-随记/image-20210307220719299.png" alt="image-20210307220719299" style="zoom: 67%;" />



#### 操作系统模型

**三层：**

<img src="Unix初级教程-随记/image-20210307215009457.png" alt="image-20210307215009457" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210307215242025.png" alt="image-20210307215242025" style="zoom: 67%;" />



#### 虚拟内存（页）

<img src="Unix初级教程-随记/image-20210307221049116.png" alt="image-20210307221049116" style="zoom:67%;" />



## 第二章 UNIX操作系统

### Unix初期

<img src="Unix初级教程-随记/image-20210310213819020.png" alt="image-20210310213819020" style="zoom:80%;" />



### Unix重写

<img src="Unix初级教程-随记/image-20210310214023877.png" alt="image-20210310214023877" style="zoom:80%;" />



**Unix操作系统有 2 个主要版本：**

<img src="Unix初级教程-随记/image-20210310214121908.png" alt="image-20210310214121908" style="zoom:80%;" />

**SVID**

AT&T的**UNIX标准**称为系统V用户接口定义(SVID, System V Interface Definition)



**POSIX**

其他一些UNIX操作系统和UNEX相关产品厂商联合开发了一个称为**计算环境中的可移植操作系统接口**(POSIX, Portable Operating System Interface for Computer Envimnments)。POSIX 在很大程度上是基于SVID的。



### 其他Unix系统

<img src="Unix初级教程-随记/image-20210310214731604.png" alt="image-20210310214731604" style="zoom: 80%;" />

<img src="Unix初级教程-随记/image-20210310214759904.png" alt="image-20210310214759904" style="zoom:67%;" />





### Unix操作系统概要

<img src="Unix初级教程-随记/image-20210310220739229.png" alt="image-20210310220739229" style="zoom:80%;" />



#### Unix系统采用的是分层结构

+ **内核**

  <img src="Unix初级教程-随记/image-20210310222245894.png" alt="image-20210310222245894" style="zoom:80%;" />

+ **常驻模块**

  <img src="Unix初级教程-随记/image-20210310222332586.png" alt="image-20210310222332586" style="zoom:80%;" />

+ **工具层（shell）**

  <img src="Unix初级教程-随记/image-20210310222422046.png" alt="image-20210310222422046" style="zoom:80%;" />

+ **虚拟计算机**

  <img src="Unix初级教程-随记/image-20210310222608896.png" alt="image-20210310222608896" style="zoom:80%;" />

+ **进程**

  <img src="Unix初级教程-随记/image-20210310222706473.png" alt="image-20210310222706473" style="zoom:80%;" />





### Unix的系统特性

**部分重点词：**

+ 系统工具：系统工具也称为命令

<img src="Unix初级教程-随记/image-20210310223149140.png" alt="image-20210310223149140" style="zoom:67%;" />

<img src="Unix初级教程-随记/image-20210317211906669.png" alt="image-20210317211906669" style="zoom:67%;" />







## 第三章 UNIX入门

### UNIX系统的登录和退出

#### 登录

<img src="Unix初级教程-随记/image-20210317214515021.png" alt="image-20210317214515021" style="zoom:67%;" />





**输入用户名：**

<img src="Unix初级教程-随记/image-20210317214649487.png" alt="image-20210317214649487" style="zoom: 80%;" />

<img src="Unix初级教程-随记/image-20210317214942417.png" alt="image-20210317214942417" style="zoom:80%;" />

**输入口令（密码）：**

<img src="Unix初级教程-随记/image-20210317214723035.png" alt="image-20210317214723035" style="zoom: 80%;" />

<img src="Unix初级教程-随记/image-20210317214856565.png" alt="image-20210317214856565" style="zoom: 80%;" />





**UNIX 系统通过显示命令提示符来表示可接受用户的命令输入。标准提示通常是一个美元符号S或百分号%，它会显示在每一行的第一个字符处**

<img src="Unix初级教程-随记/image-20210317215158672.png" alt="image-20210317215158672" style="zoom:80%;" />



#### 修改口令

+ **输入passwd后，输入旧口令**

  <img src="Unix初级教程-随记/image-20210317215855412.png" alt="image-20210317215855412" style="zoom:80%;" />

+ **旧口令确认正确后，输入新口令：**

  ![image-20210317220035164](Unix初级教程-随记/image-20210317220035164.png)

  两次输入的新口令相同，则UNIX系统将成功修改用户名口令

+ **口令格式限制：**

  <img src="Unix初级教程-随记/image-20210317220509462.png" alt="image-20210317220509462" style="zoom:80%;" />



#### 退出系统

**在命令符下按组合键\[ Ctr-d](即同时按下Ctrl 键和字符键d)退出系统	**

**【注：用户只能在显示命令提示符时退出系统，而不能在进程执行过程中退出系统。**】

<img src="Unix初级教程-随记/image-20210317221130539.png" alt="image-20210317221130539" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210317221300142.png" alt="image-20210317221300142" style="zoom: 67%;" />





### 一些简单的UNIX命令

**UNIX把回车键解释为命令行的结束符。**

用户每输入一个UNIX命令，系统就执行相应的功能，然后显示一个新的命令提示符，表示可输入下一个命令。



#### 基本的命令行格式

<img src="Unix初级教程-随记/image-20210317225906654.png" alt="image-20210317225906654"  />



<img src="Unix初级教程-随记/image-20210317230135080.png" alt="image-20210317230135080" style="zoom: 80%;" />m



+ **命令名：**

  <img src="Unix初级教程-随记/image-20210317230834493.png" alt="image-20210317230834493" style="zoom: 80%;" />

+ **命令选项：**

  <img src="Unix初级教程-随记/image-20210317231122006.png" alt="image-20210317231122006" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210317234216069.png" alt="image-20210317234216069" style="zoom:80%;" />

  eg.	`who -H`

+ **命令参数：**

  <img src="Unix初级教程-随记/image-20210317232810993.png" alt="image-20210317232810993" style="zoom:80%;" />





#####  显示日期和时间:	date命令

+ `$ date`

  <img src="Unix初级教程-随记/image-20210317232939507.png" alt="image-20210317232939507" style="zoom:80%;" />



##### 用户信息:	who命令

+ `$ who`

  <img src="Unix初级教程-随记/image-20210317233838498.png" alt="image-20210317233838498" style="zoom: 80%;" />

+ `$ who am i` / `who am I`

  <img src="Unix初级教程-随记/image-20210317233956903.png" alt="image-20210317233956903" style="zoom:80%;" />

+ **其他命令：**

  <img src="Unix初级教程-随记/image-20210317234040226.png" alt="image-20210317234040226" style="zoom:80%;" /><img src="Unix初级教程-随记/image-20210317234216069.png" alt="image-20210317234216069" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210317234613744.png" alt="image-20210317234613744" style="zoom:67%;" />



##### 显示日历：cal命令

+ `$ cal MM YYYY`

  <img src="Unix初级教程-随记/image-20210317234953429.png" alt="image-20210317234953429" style="zoom: 80%;" />

  <img src="Unix初级教程-随记/image-20210317235141939.png" alt="image-20210317235141939" style="zoom: 80%;" />





### UNIX帮助信息

<img src="Unix初级教程-随记/image-20210317235334519.png" alt="image-20210317235334519" style="zoom:80%;" />



#### learn 命令

<img src="Unix初级教程-随记/image-20210317235510354.png" alt="image-20210317235510354" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210317235554491.png" alt="image-20210317235554491" style="zoom: 80%;" />



#### help 命令

<img src="Unix初级教程-随记/image-20210317235850728.png" alt="image-20210317235850728" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210317235921917.png" alt="image-20210317235921917" style="zoom:80%;" />



#### 使用电子手册：man命令

<img src="Unix初级教程-随记/image-20210318000239916.png" alt="image-20210318000239916" style="zoom:80%;" />

+ 输入`$ man cal`

  <img src="Unix初级教程-随记/image-20210318000414312.png" alt="image-20210318000414312" style="zoom: 80%;" />





### 更正键盘输入错误

+ **删除字符：[Back Space] / [Ctrl-h]**

  <img src="Unix初级教程-随记/image-20210318000724838.png" alt="image-20210318000724838" style="zoom:80%;" />

+ **删除一行：[Ctrl-u]**

+ **中断程序运行：[Del] / [Ctrl-c]**

  <img src="Unix初级教程-随记/image-20210318001100237.png" alt="image-20210318001100237" style="zoom:80%;" />

  

  <img src="Unix初级教程-随记/image-20210318001108370.png" alt="image-20210318001108370" style="zoom:80%;" />





### 使用 shell 和系统工具

**shell是一个命令解释程序。UNIX命令由部分shell命令和系统工具组成，系统工具又是由shell查找和加载执行的可执行程序**

<img src="Unix初级教程-随记/image-20210318001526560.png" alt="image-20210318001526560" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210318001634079.png" alt="image-20210318001634079" style="zoom:80%;" />



**shell的种类：**

<img src="Unix初级教程-随记/image-20210318001954153.png" alt="image-20210318001954153" style="zoom:80%;" />

+ **Bourne shell**

  <img src="Unix初级教程-随记/image-20210318002037985.png" alt="image-20210318002037985" style="zoom:80%;" />

+ **Korn shell**

  <img src="Unix初级教程-随记/image-20210318002125373.png" alt="image-20210318002125373" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210318002228834.png" alt="image-20210318002228834" style="zoom: 80%;" />

+ **C shell**

  <img src="Unix初级教程-随记/image-20210318002202717.png" alt="image-20210318002202717" style="zoom:80%;" />





### 登录过程

<img src="Unix初级教程-随记/image-20210318191056082.png" alt="image-20210318191056082" style="zoom:80%;" />



+ **当UNIX系统完全启动后（init程序、getty程序）**

  <img src="Unix初级教程-随记/image-20210318191816737.png" alt="image-20210318191816737" style="zoom:80%;" />

+ **用户输入用户名时（getty程序、login程序）**

  <img src="Unix初级教程-随记/image-20210318192054080.png" alt="image-20210318192054080" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210318192110704.png" alt="image-20210318192110704" style="zoom:80%;" />

  

+ **用户输入口令后（login程序、shell程序）**

  <img src="Unix初级教程-随记/image-20210318192221283.png" alt="image-20210318192221283" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210318192415913.png" alt="image-20210318192415913" style="zoom:75%;" />

+ **当用户退出系统**

  <img src="Unix初级教程-随记/image-20210318192547862.png" alt="image-20210318192547862" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210318192733236.png" alt="image-20210318192733236" style="zoom:80%;" />





## 第四章	Vi编辑器入门

### 什么是编辑器

<img src="Unix初级教程-随记/image-20210319113201332.png" alt="image-20210319113201332" style="zoom:80%;" />

+ **行编辑器**

  <img src="Unix初级教程-随记/image-20210319113302890.png" alt="image-20210319113302890" style="zoom:80%;" />

+ **全屏编辑器**

  <img src="Unix初级教程-随记/image-20210319113348597.png" alt="image-20210319113348597" style="zoom:80%;" />





#### UNIX支持的编辑器

<img src="Unix初级教程-随记/image-20210319113708652.png" alt="image-20210319113708652" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210319113806818.png" alt="image-20210319113806818" style="zoom:80%;" />





### vi编辑器

**vi有两个版本：**

<img src="Unix初级教程-随记/image-20210319114626842.png" alt="image-20210319114626842" style="zoom:80%;" />



#### vi的工作模式

![image-20210319114803101](Unix初级教程-随记/image-20210319114803101.png)

+ **命令模式**

  <img src="Unix初级教程-随记/image-20210319114922692.png" alt="image-20210319114922692" style="zoom:90%;" />

+ **文本输入模式**

  <img src="Unix初级教程-随记/image-20210319115043985.png" alt="image-20210319115043985" style="zoom:90%;" />



**状态行：**

![image-20210319115116384](Unix初级教程-随记/image-20210319115116384.png)





### 基本vi编辑器命令

#### 启动vi

**输入`vi 文件名`**

<img src="Unix初级教程-随记/image-20210319120233008.png" alt="image-20210319120233008" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210319120316004.png" alt="image-20210319120316004" style="zoom:80%;" />





#### 退出vi（下面的命令模式中有讲解更多的退出方式）

按[Esc]，然后输入`:wq`

<img src="Unix初级教程-随记/image-20210319121233758.png" alt="image-20210319121233758" style="zoom:90%;" />





#### 文本输入模式

<img src="Unix初级教程-随记/image-20210319121543056.png" alt="image-20210319121543056" style="zoom:90%;" />



表4.2总结了**从vi的命令模式切换到文本输人模式**状态下的命令键**（按[Esc]键保证vi处于命令模式）**

![image-20210320170849985](Unix初级教程-随记/image-20210320170849985.png)

**在文本输入模式下，使用空格键、[Tab]键、回退键和回车键**

和正常windows下的文本文档和word中的效果一样





#### 命令模式（注意以下所有命令只有在命令模式下才起作用）

<img src="Unix初级教程-随记/image-20210320215347284.png" alt="image-20210320215347284" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210320222624056.png" alt="image-20210320222624056" style="zoom:80%;" />



##### **光标移动键**

<img src="Unix初级教程-随记/image-20210320215733172.png" alt="image-20210320215733172" style="zoom:90%;" />





##### 文本修改

<img src="Unix初级教程-随记/image-20210320220229703.png" alt="image-20210320220229703" style="zoom:90%;" />

**注意：**

+ **按r后，再按一个字符便会替换光标所在的字符，此时仍处于命令模式状态**
+ **而按R后，vi会进去文本输入模式，需要再按[Esc]返回到命令模式**





##### 搜索字符串：/和？的使用

<img src="Unix初级教程-随记/image-20210320221042151.png" alt="image-20210320221042151" style="zoom:90%;" />



##### 退出vi

**表4.5中前4个方法的使用，均为在命令行模式下，输入`：`后再输入对应的键，然后按回车，最后一个ZZ则只需要在命令行模式下直接连按即执行**

<img src="Unix初级教程-随记/image-20210320221253639.png" alt="image-20210320221253639"  />

<img src="Unix初级教程-随记/image-20210320221444808.png" alt="image-20210320221444808" style="zoom:80%;" />





#### 存储缓冲区

<img src="Unix初级教程-随记/image-20210320223109154.png" alt="image-20210320223109154" style="zoom:80%;" />



<img src="Unix初级教程-随记/image-20210320223316307.png" alt="image-20210320223316307" style="zoom:90%;" />





### 基本命令总结

<img src="Unix初级教程-随记/image-20210320223411733.png" alt="image-20210320223411733" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210320223458718.png" alt="image-20210320223458718" style="zoom:80%;" />





## 第五章	UNIX文件系统介绍

### 磁盘组织

<img src="Unix初级教程-随记/image-20210318203415216.png" alt="image-20210318203415216" style="zoom:80%;" />





### UNIX里的文件类型

**UNIX有三类文件：规则文件，目录文件，特殊文件**

<img src="Unix初级教程-随记/image-20210321222157474.png" alt="image-20210321222157474" style="zoom:90%;" />





### 目录详述

<img src="Unix初级教程-随记/image-20210321222348752.png" alt="image-20210321222348752" style="zoom:90%;" />



#### 用户主目录

<img src="Unix初级教程-随记/image-20210321222659373.png" alt="image-20210321222659373" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210321222739168.png" alt="image-20210321222739168" style="zoom:80%;" />



#### 工作目录

<img src="Unix初级教程-随记/image-20210321222854468.png" alt="image-20210321222854468" style="zoom:80%;" />





#### 路径和路径名

<img src="Unix初级教程-随记/image-20210321223148938.png" alt="image-20210321223148938" style="zoom:90%;" />

<img src="Unix初级教程-随记/image-20210321223234490.png" alt="image-20210321223234490" style="zoom:90%;" />



**相对路径名和绝对路径名：**

![image-20210321223422031](Unix初级教程-随记/image-20210321223422031.png)





#### 使用文件和目录名

<img src="Unix初级教程-随记/image-20210321234819407.png" alt="image-20210321234819407" style="zoom:90%;" />



![image-20210321234951970](Unix初级教程-随记/image-20210321234951970.png)

<img src="Unix初级教程-随记/image-20210321235003401.png" alt="image-20210321235003401" style="zoom:80%;" /><img src="Unix初级教程-随记/image-20210321235014949.png" alt="image-20210321235014949" style="zoom:80%;" />



<img src="Unix初级教程-随记/image-20210321235148358.png" alt="image-20210321235148358" style="zoom:90%;" />

<img src="Unix初级教程-随记/image-20210321235708437.png" alt="image-20210321235708437" style="zoom:90%;" />



<img src="Unix初级教程-随记/image-20210321235934295.png" alt="image-20210321235934295" style="zoom:90%;" />





### 目录命令

#### 显示目录路径名：pwd命令

<img src="Unix初级教程-随记/image-20210322001047912.png" alt="image-20210322001047912" style="zoom:90%;" />



#### 改变工作目录：cd命令

<img src="Unix初级教程-随记/image-20210322001454663.png" alt="image-20210322001454663" style="zoom:80%;" />

#### 创建目录：mkdir命令

![image-20210322002020553](Unix初级教程-随记/image-20210322002020553.png)

![image-20210322002527699](Unix初级教程-随记/image-20210322002527699.png)

```linux
$ mkdir 子目录名 .................在当前工作目录创建一个新的子目录

$ mkdir memos/test ..................在memos目录下创建名为test的子目录

$ mkdir -p xx/yy/zz ...................创建目录xx；xx下创建目录yy;yy目录下创建目录zz
```





#### 删除目录：rmdir命令

<img src="Unix初级教程-随记/image-20210322095102136.png" alt="image-20210322095102136" style="zoom:90%;" />

<img src="Unix初级教程-随记/image-20210322181425139.png" alt="image-20210322181425139" style="zoom:90%;" />



#### 目录列表：ls命令

<img src="Unix初级教程-随记/image-20210322180917944.png" alt="image-20210322180917944" style="zoom:90%;" />

![image-20210322181324149](Unix初级教程-随记/image-20210322181324149.png)



<img src="Unix初级教程-随记/image-20210322181528280.png" alt="image-20210322181528280" style="zoom:90%;" />

<img src="Unix初级教程-随记/image-20210322181648561.png" alt="image-20210322181648561" style="zoom:90%;" />



+ **`ls -l`**

  <img src="Unix初级教程-随记/image-20210322183553482.png" alt="image-20210322183553482" style="zoom:90%;" />

  + **第一列：**

    <img src="Unix初级教程-随记/image-20210322183707870.png" alt="image-20210322183707870" style="zoom:80%;" />

    <img src="Unix初级教程-随记/image-20210322184130834.png" alt="image-20210322184130834" style="zoom:80%;" />

  + **其余列：**

    ![image-20210322184411499](Unix初级教程-随记/image-20210322184411499.png)

+ **隐藏文件**

  <img src="Unix初级教程-随记/image-20210322184952699.png" alt="image-20210322184952699" style="zoom:90%;" />



+ **使用多个选项**

  <img src="Unix初级教程-随记/image-20210322185603535.png" alt="image-20210322185603535" style="zoom:80%;" />





### 显示文件内容

<img src="Unix初级教程-随记/image-20210323002457099.png" alt="image-20210323002457099" style="zoom:90%;" />





### 打印文件内容

#### 打印：lp命令

<img src="Unix初级教程-随记/image-20210323002626012.png" alt="image-20210323002626012" style="zoom:90%;" />

**同理一行命令中可以指定多个文件**

<img src="Unix初级教程-随记/image-20210323002738454.png" alt="image-20210323002738454" style="zoom:90%;" />



#### 取消打印请求

![image-20210323002957671](Unix初级教程-随记/image-20210323002957671.png)

![image-20210323003007590](Unix初级教程-随记/image-20210323003007590.png)



#### 获取打印机的状态：lpstat命令

<img src="Unix初级教程-随记/image-20210323003051744.png" alt="image-20210323003051744" style="zoom:90%;" />





### 删除文件：rm命令

![image-20210323003149603](Unix初级教程-随记/image-20210323003149603.png)

![image-20210323003305076](Unix初级教程-随记/image-20210323003305076.png)

![image-20210323003227813](Unix初级教程-随记/image-20210323003227813.png)

<img src="Unix初级教程-随记/image-20210323003213164.png" alt="image-20210323003213164" style="zoom:110%;" />







### 基本命令总结

<img src="Unix初级教程-随记/image-20210323003538708.png" alt="image-20210323003538708" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210323003512650.png" alt="image-20210323003512650" style="zoom:80%;" />





## 第六章 vi编辑器：高级使用

### 更多有关 vi 编辑器的知识

<img src="Unix初级教程-随记/image-20210324233556828.png" alt="image-20210324233556828" style="zoom:90%;" />



#### 调用 vi 编辑器

**vi 编辑器中新建文件**

<img src="Unix初级教程-随记/image-20210324234126101.png" alt="image-20210324234126101" style="zoom:80%;" />



**在 vi 中复制文件**

<img src="Unix初级教程-随记/image-20210324235225528.png" alt="image-20210324235225528" style="zoom:80%;" />





#### 使用 vi 调用选项

+ **只读选项：-R**

  <img src="Unix初级教程-随记/image-20210324235452967.png" alt="image-20210324235452967" style="zoom:90%;" />

+ **命令选项：-c**

  <img src="Unix初级教程-随记/image-20210324235808665.png" alt="image-20210324235808665" style="zoom:90%;" />



#### 编辑多文档

<img src="Unix初级教程-随记/image-20210325000159477.png" alt="image-20210325000159477" style="zoom:90%;" />

![image-20210325000248055](Unix初级教程-随记/image-20210325000248055.png)



**编辑另一个文件：:e**

<img src="Unix初级教程-随记/image-20210325000622268.png" alt="image-20210325000622268" style="zoom:90%;" />



**读取另一个文件：:r**

<img src="Unix初级教程-随记/image-20210325000905005.png" alt="image-20210325000905005" style="zoom: 90%;" />



**写入另一个文件：:w**

<img src="Unix初级教程-随记/image-20210325001102371.png" alt="image-20210325001102371" style="zoom:90%;" />





### 重排文本（剪切，复制，粘贴，清空）

<img src="Unix初级教程-随记/image-20210325001703562.png" alt="image-20210325001703562" style="zoom:80%;" />



#### 移动行：dd、p 或 P

<img src="Unix初级教程-随记/image-20210325001837864.png" alt="image-20210325001837864" style="zoom: 80%;" />



#### 复制行：yy、p 或 P

<img src="Unix初级教程-随记/image-20210325002139719.png" alt="image-20210325002139719" style="zoom:80%;" />





### vi 操作符的域

![image-20210325213614152](Unix初级教程-随记/image-20210325213614152.png)

![image-20210325213623559](Unix初级教程-随记/image-20210325213623559.png)

**部分实例：**

+ `d0`

  <img src="Unix初级教程-随记/image-20210325214056042.png" alt="image-20210325214056042" style="zoom: 80%;" />

+ `dw`

  <img src="Unix初级教程-随记/image-20210415082227700.png" alt="image-20210415082227700" style="zoom:80%;" />

+ `3dw`

  <img src="Unix初级教程-随记/image-20210415082359276.png" alt="image-20210415082359276" style="zoom:80%;" />



**带域控制键的修改操作符 `c`**

<img src="Unix初级教程-随记/image-20210415083328837.png" alt="image-20210415083328837" style="zoom:80%;" />

+ **实例：**

  <img src="Unix初级教程-随记/image-20210415083352264.png" alt="image-20210415083352264" style="zoom:80%;" />



### 在 vi 中使用缓冲区

**vi 中有两类临时缓冲区：数字编号缓冲区和命名缓冲区**



#### 数字编号缓冲区

<img src="Unix初级教程-随记/image-20210415083808638.png" alt="image-20210415083808638" style="zoom:80%;" />

+ 每次拾取文本到临时缓冲区中时，vi 必须将所有缓冲区中的内容依次后移一个缓冲区来空出缓冲区 1 ，接着将新内容放到缓冲区 1 中，后移过程如果缓冲区 9 中有内容将被舍弃。

<img src="Unix初级教程-随记/image-20210415083858971.png" alt="image-20210415083858971" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415084053865.png" alt="image-20210415084053865" style="zoom:80%;" />



#### 字母序缓冲区

<img src="Unix初级教程-随记/image-20210415084751831.png" alt="image-20210415084751831" style="zoom:80%;" />





### 光标定位键

+ **vi 翻页键**

  <img src="Unix初级教程-随记/image-20210415084905181.png" alt="image-20210415084905181" style="zoom:80%;" />

+ `行号G`

  <img src="Unix初级教程-随记/image-20210415085021153.png" alt="image-20210415085021153" style="zoom:80%;" />

+ [Ctrl - g]

  ![image-20210415085105546](Unix初级教程-随记/image-20210415085105546.png)



### 定制 vi 编辑器

+ `set all`

  <img src="Unix初级教程-随记/image-20210415085718479.png" alt="image-20210415085718479" style="zoom:80%;" />



**set设置选项命令：**

<img src="Unix初级教程-随记/image-20210415085836911.png" alt="image-20210415085836911" style="zoom:80%;" />

+ 布尔选项

  <img src="Unix初级教程-随记/image-20210415085918896.png" alt="image-20210415085918896" style="zoom:80%;" />

+ 数字式选项

  <img src="Unix初级教程-随记/image-20210415085937775.png" alt="image-20210415085937775" style="zoom: 80%;" />

+ 串选项

  <img src="Unix初级教程-随记/image-20210415090012854.png" alt="image-20210415090012854" style="zoom:80%;" />



**set其他命名：**

<img src="Unix初级教程-随记/image-20210415090341451.png" alt="image-20210415090341451" style="zoom:80%;" />





#### 设置 vi 环境

<img src="Unix初级教程-随记/image-20210415091212334.png" alt="image-20210415091212334" style="zoom:80%;" />



**一些有用的 vi 参数：**

<img src="Unix初级教程-随记/image-20210415091308894.png" alt="image-20210415091308894" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415091343198.png" alt="image-20210415091343198" style="zoom: 67%;" />



#### 行长度和行回绕

<img src="Unix初级教程-随记/image-20210415091843977.png" alt="image-20210415091843977" style="zoom:80%;" />

+ **wrapmargin：**

  <img src="Unix初级教程-随记/image-20210415091947164.png" alt="image-20210415091947164" style="zoom:80%;" />



#### 缩写与宏

![image-20210415093453106](Unix初级教程-随记/image-20210415093453106.png)



+ **缩写操作符（db）：**

  <img src="Unix初级教程-随记/image-20210415093851011.png" alt="image-20210415093851011" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415093941501.png" alt="image-20210415093941501" style="zoom:80%;" />

+ **宏操作符（map）：**

  <img src="Unix初级教程-随记/image-20210415094404964.png" alt="image-20210415094404964" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415094939290.png" alt="image-20210415094939290" style="zoom:90%;" />

  <img src="Unix初级教程-随记/image-20210415094950457.png" alt="image-20210415094950457" style="zoom: 80%;" />

  **实例：**

  <img src="Unix初级教程-随记/image-20210415094849584.png" alt="image-20210415094849584" style="zoom:67%;" />





#### .exrc文件

<img src="Unix初级教程-随记/image-20210415095301754.png" alt="image-20210415095301754" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415095229956.png" alt="image-20210415095229956" style="zoom:80%;" />



**实例：**

<img src="Unix初级教程-随记/image-20210415095422793.png" alt="image-20210415095422793" style="zoom:80%;" />





### 最后的 vi 命令

#### 运行shell

<img src="Unix初级教程-随记/image-20210415144642462.png" alt="image-20210415144642462" style="zoom:80%;" />





#### 行连接

<img src="Unix初级教程-随记/image-20210415145559886.png" alt="image-20210415145559886" style="zoom:80%;" />





#### 搜索和替换

<img src="Unix初级教程-随记/image-20210415150014344.png" alt="image-20210415150014344" style="zoom:80%;" />





### 基本命名总结

<img src="Unix初级教程-随记/image-20210415150058188.png" alt="image-20210415150058188" style="zoom: 80%;" />





## 第七章 UNIX文件系统（续）

### 读取文件

<img src="Unix初级教程-随记/image-20210415151615015.png" alt="image-20210415151615015" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415151703925.png" alt="image-20210415151703925" style="zoom:80%;" />



#### vi 编辑器的只读版：view命令

<img src="Unix初级教程-随记/image-20210415151830432.png" alt="image-20210415151830432" style="zoom:80%;" />



+ **读取文件：`pg`命令**

  <img src="Unix初级教程-随记/image-20210415151945618.png" alt="image-20210415151945618" style="zoom:80%;" />

  ![image-20210415151959614](Unix初级教程-随记/image-20210415151959614.png)

  ![image-20210415152023959](Unix初级教程-随记/image-20210415152023959.png)

  <img src="Unix初级教程-随记/image-20210415152548269.png" alt="image-20210415152548269" style="zoom:80%;" />

  **实例：**

  <img src="Unix初级教程-随记/image-20210415152525889.png" alt="image-20210415152525889" style="zoom:80%;" />

+ **指定页和行数**

  <img src="Unix初级教程-随记/image-20210415153017501.png" alt="image-20210415153017501" style="zoom:80%;" />





### shell 重定向

<img src="Unix初级教程-随记/image-20210415154307131.png" alt="image-20210415154307131" style="zoom:80%;" />



#### 输出重定向

<img src="Unix初级教程-随记/image-20210415154522269.png" alt="image-20210415154522269" style="zoom:80%;" />



**实例：**

+ **`>`**

<img src="Unix初级教程-随记/image-20210415154649137.png" alt="image-20210415154649137" style="zoom:80%;" />

+ **`>>`**

  ![image-20210415154811644](Unix初级教程-随记/image-20210415154811644.png)





#### 输入重定向

![image-20210415155359941](Unix初级教程-随记/image-20210415155359941.png)

![image-20210415155409632](Unix初级教程-随记/image-20210415155409632.png)



**实例：**

<img src="Unix初级教程-随记/image-20210415161518756.png" alt="image-20210415161518756" style="zoom:80%;" />



**cat 命令和输入重定向结合**

+ **创建文件**

  <img src="Unix初级教程-随记/image-20210415161746292.png" alt="image-20210415161746292"  />

  **实例：**

  <img src="Unix初级教程-随记/image-20210415161838308.png" alt="image-20210415161838308" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415161901207.png" alt="image-20210415161901207" style="zoom:80%;" />

+ **复制文件**

  **实例：**

  + <img src="Unix初级教程-随记/image-20210415162206256.png" alt="image-20210415162206256" style="zoom:80%;" />

  + <img src="Unix初级教程-随记/image-20210415162229341.png" alt="image-20210415162229341" style="zoom:80%;" />
  + <img src="Unix初级教程-随记/image-20210415162423473.png" alt="image-20210415162423473" style="zoom:80%;" />



### 文件格式化

<img src="Unix初级教程-随记/image-20210415162713263.png" alt="image-20210415162713263" style="zoom:80%;" />



+ **`pr`命令**

  <img src="Unix初级教程-随记/image-20210415163118998.png" alt="image-20210415163118998" style="zoom:80%;" />

  **实例：**

  <img src="Unix初级教程-随记/image-20210415163259071.png" alt="image-20210415163259071" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415163313003.png" alt="image-20210415163313003" style="zoom:80%;" />

  **pr选项：**

  <img src="Unix初级教程-随记/image-20210415163349883.png" alt="image-20210415163349883" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415163429335.png" alt="image-20210415163429335" style="zoom:80%;" />







### 文件处理命令

![image-20210415163706930](Unix初级教程-随记/image-20210415163706930.png)



+ **复制文件：`cp`命令**

  <img src="Unix初级教程-随记/image-20210415164422349.png" alt="image-20210415164422349" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415164432197.png" alt="image-20210415164432197" style="zoom:80%;" />

  + **cp选项：**

    ![image-20210415164656629](Unix初级教程-随记/image-20210415164656629.png)

    <img src="Unix初级教程-随记/image-20210415164729690.png" alt="image-20210415164729690" style="zoom:80%;" />

    <img src="Unix初级教程-随记/image-20210415164815751.png" alt="image-20210415164815751" style="zoom:80%;" />

+ **移动文件：`mv`命令**

  <img src="Unix初级教程-随记/image-20210415164957826.png" alt="image-20210415164957826" style="zoom:80%;" />

+ **链接文件：`ln`命令**

  <img src="Unix初级教程-随记/image-20210415165320594.png" alt="image-20210415165320594" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415165414206.png" alt="image-20210415165414206" style="zoom:80%;" />

+ **计算字数：`wc`命令**

  ![image-20210415165558707](Unix初级教程-随记/image-20210415165558707.png)

  + <img src="Unix初级教程-随记/image-20210415165656334.png" alt="image-20210415165656334" style="zoom:80%;" />

  + <img src="Unix初级教程-随记/image-20210415165923664.png" alt="image-20210415165923664" style="zoom:80%;" />

  + **wc选项：**

    <img src="Unix初级教程-随记/image-20210415170517818.png" alt="image-20210415170517818" style="zoom:80%;" />





### 文件名置换

![image-20210415170749514](Unix初级教程-随记/image-20210415170749514.png)

+ **`？`元字符**

  <img src="Unix初级教程-随记/image-20210415170857338.png" alt="image-20210415170857338" style="zoom: 67%;" />

+ **`*`元字符**

  <img src="Unix初级教程-随记/image-20210415170956318.png" alt="image-20210415170956318" style="zoom:67%;" />

  <img src="Unix初级教程-随记/image-20210415171239821.png" alt="image-20210415171239821" style="zoom:67%;" />

+ `[]`元字符

  <img src="Unix初级教程-随记/image-20210415171325560.png" alt="image-20210415171325560" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415171414192.png" alt="image-20210415171414192" style="zoom:67%;" />

  <img src="Unix初级教程-随记/image-20210415171525805.png" alt="image-20210415171525805" style="zoom:67%;" />

  



### 其他文件操作命令

+ **寻找文件：find命令**

  <img src="Unix初级教程-随记/image-20210415171803961.png" alt="image-20210415171803961" style="zoom:67%;" />

  + **查找选项：**

    <img src="Unix初级教程-随记/image-20210415171825034.png" alt="image-20210415171825034"  />

    <img src="Unix初级教程-随记/image-20210415172003954.png" alt="image-20210415172003954" style="zoom:80%;" />

    <img src="Unix初级教程-随记/image-20210415172140105.png" alt="image-20210415172140105" style="zoom:80%;" />

    <img src="Unix初级教程-随记/image-20210415172220448.png" alt="image-20210415172220448" style="zoom: 80%;" />

    <img src="Unix初级教程-随记/image-20210415172254662.png" alt="image-20210415172254662" style="zoom:80%;" />

    <img src="Unix初级教程-随记/image-20210415172357677.png" alt="image-20210415172357677" style="zoom:80%;" />

  + **动作选项**

    ![image-20210415172524799](Unix初级教程-随记/image-20210415172524799.png)

    P135

+ **显示文件头部：`head`命令**

  <img src="Unix初级教程-随记/image-20210415172722085.png" alt="image-20210415172722085" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415172753692.png" alt="image-20210415172753692" style="zoom:80%;" />

+ **显示文件的尾部：`tail`命令**

  <img src="Unix初级教程-随记/image-20210415172938388.png" alt="image-20210415172938388" style="zoom:67%;" />

  <img src="Unix初级教程-随记/image-20210415173001098.png" alt="image-20210415173001098" style="zoom:80%;" />

+ **选择文件的一部分：`cut`命令**

  <img src="Unix初级教程-随记/image-20210415173609700.png" alt="image-20210415173609700" style="zoom:80%;" />

  **cut选项**

  <img src="Unix初级教程-随记/image-20210415173503495.png" alt="image-20210415173503495" style="zoom: 80%;" />

  ![image-20210415173706012](Unix初级教程-随记/image-20210415173706012.png)

  <img src="Unix初级教程-随记/image-20210415173754637.png" alt="image-20210415173754637" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415173858230.png" alt="image-20210415173858230" style="zoom:80%;" />

+ **链接文件：paste命令**

  ![image-20210415173940693](Unix初级教程-随记/image-20210415173940693.png)

  ![image-20210415173953242](Unix初级教程-随记/image-20210415173953242.png)

  ![image-20210415180419055](Unix初级教程-随记/image-20210415180419055.png)

+ **另一个页面查看工具：more命令**

  <img src="Unix初级教程-随记/image-20210415180442570.png" alt="image-20210415180442570" style="zoom:80%;" />





### UNIX内部：文件系统

![image-20210415180648317](Unix初级教程-随记/image-20210415180648317.png)





#### UNIX磁盘结构

![image-20210415180800882](Unix初级教程-随记/image-20210415180800882.png)

+ **主引导块**

  <img src="Unix初级教程-随记/image-20210415180820691.png" alt="image-20210415180820691" style="zoom:80%;" />

+ **超级块**

  <img src="Unix初级教程-随记/image-20210415180917149.png" alt="image-20210415180917149" style="zoom:80%;" />

+ **i 节点列表块**

  <img src="Unix初级教程-随记/image-20210415181014667.png" alt="image-20210415181014667" style="zoom:80%;" />

+ **i 节点和目录**

  <img src="Unix初级教程-随记/image-20210415181037791.png" alt="image-20210415181037791" style="zoom:80%;" />





#### 整体过程

<img src="Unix初级教程-随记/image-20210415181344873.png" alt="image-20210415181344873" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415181612462.png" alt="image-20210415181612462" style="zoom:80%;" />



+ `ls -i`

  <img src="Unix初级教程-随记/image-20210415181709945.png" alt="image-20210415181709945" style="zoom:80%;" />





### 基本命令总结

<img src="Unix初级教程-随记/image-20210415181909673.png" alt="image-20210415181909673" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415181935776.png" alt="image-20210415181935776" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415181955908.png" alt="image-20210415181955908" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415182005197.png" alt="image-20210415182005197" style="zoom:80%;" />





## 第八章 探索 shell

### UNIX shell

<img src="Unix初级教程-随记/image-20210415192117591.png" alt="image-20210415192117591" style="zoom:80%;" />



**用户与操作系统通过shell进行通信**

<img src="Unix初级教程-随记/image-20210415192156582.png" alt="image-20210415192156582" style="zoom:80%;" />



<img src="Unix初级教程-随记/image-20210415192615141.png" alt="image-20210415192615141" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415193124835.png" alt="image-20210415193124835" style="zoom:80%;" />



#### shell的主要功能

<img src="Unix初级教程-随记/image-20210415193439460.png" alt="image-20210415193439460" style="zoom:80%;" />



**shell的主要特征：**

<img src="Unix初级教程-随记/image-20210415194158601.png" alt="image-20210415194158601" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415194556797.png" alt="image-20210415194556797" style="zoom:80%;" />





+ **显示信息：`echo`命令**

  <img src="Unix初级教程-随记/image-20210415194846594.png" alt="image-20210415194846594" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415194920603.png" alt="image-20210415194920603" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415195026720.png" alt="image-20210415195026720" style="zoom:80%;" />

  + **消除元字符的特殊含义**

    <img src="Unix初级教程-随记/image-20210415195326894.png" alt="image-20210415195326894" style="zoom:80%;" />

    + **反斜杠**

      <img src="Unix初级教程-随记/image-20210415195420280.png" alt="image-20210415195420280" style="zoom:80%;" />

      <img src="Unix初级教程-随记/image-20210415195508585.png" alt="image-20210415195508585" style="zoom:80%;" />

    + **双引号**

      <img src="Unix初级教程-随记/image-20210415195847648.png" alt="image-20210415195847648" style="zoom:80%;" />

      <img src="Unix初级教程-随记/image-20210415195952953.png" alt="image-20210415195952953" style="zoom:80%;" />

    + **单引号**

      <img src="Unix初级教程-随记/image-20210415200038008.png" alt="image-20210415200038008" style="zoom:80%;" />

      <img src="Unix初级教程-随记/image-20210415200104224.png" alt="image-20210415200104224" style="zoom:80%;" />





### shell变量

<img src="Unix初级教程-随记/image-20210415202554452.png" alt="image-20210415202554452" style="zoom:80%;" />

+ **环境变量**

  <img src="Unix初级教程-随记/image-20210415202917953.png" alt="image-20210415202917953" style="zoom: 80%;" />

+ **局部变量**

  <img src="Unix初级教程-随记/image-20210415202949450.png" alt="image-20210415202949450" style="zoom:80%;" />





**显示和清除变量：set和unset命令**

![image-20210415203111920](Unix初级教程-随记/image-20210415203111920.png)

<img src="Unix初级教程-随记/image-20210415203224185.png" alt="image-20210415203224185" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415203233643.png" alt="image-20210415203233643" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415203305898.png" alt="image-20210415203305898" style="zoom:80%;" />



**给变量赋值**

<img src="Unix初级教程-随记/image-20210415203636030.png" alt="image-20210415203636030" style="zoom:80%;" />



**显示shell变量的值**

<img src="Unix初级教程-随记/image-20210415203728508.png" alt="image-20210415203728508" style="zoom:80%;" />

<img src="Unix初级教程-随记/image-20210415204034035.png" alt="image-20210415204034035" style="zoom:80%;" />





**理解标准shell变量**

<img src="Unix初级教程-随记/image-20210415205654045.png" alt="image-20210415205654045" style="zoom:80%;" />



+ **HOME变量**

  <img src="Unix初级教程-随记/image-20210415205816726.png" alt="image-20210415205816726" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415205901884.png" alt="image-20210415205901884" style="zoom:80%;" />

+ **IFS变量**

  <img src="Unix初级教程-随记/image-20210415210154984.png" alt="image-20210415210154984" style="zoom:80%;" />

  <img src="Unix初级教程-随记/image-20210415210208984.png" alt="image-20210415210208984" style="zoom:80%;" />

+ **MAIL变量**

  <img src="Unix初级教程-随记/image-20210415210259195.png" alt="image-20210415210259195" style="zoom:80%;" />

+ **MAILCHECK变量**

  <img src="Unix初级教程-随记/image-20210415210406955.png" alt="image-20210415210406955" style="zoom:80%;" />

+ **PATH变量**

  略P158~159





### 更多的元字符

P159

