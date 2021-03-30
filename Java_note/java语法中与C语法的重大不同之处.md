## java语法中与C语法的重大不同之处

### 1.字符串变量的定义

用 `String s = new String("字符串内容")/String s = "字符串内容"` 定义字符串变量



### 2.变量之间的比较（ == ）

●int、double等数字之间的比较是数字的大小

●数组以及字符串是比较它们管理的是不是同一个东西（比较指向的地址不是比较内容）。因此数组比较只能比较每一个数组元素，字符串要比较则是使用如下图所示,会输出“ture”。

`String s = new String("bye");`

`System.out.printlin(s.equal("bye"))`



### 3.输入与输出



### 4.switch-case

java中可以将字符串作为case后的条件。



### 5.变量的定义