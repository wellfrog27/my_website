---
title: 基本语法
date: 2015-02-15
author: 阮一峰
series: C语言系列教程
---

## 最简单的示例

下面是一个简单的 C 程序`hello.c`。

```c
# include <stdio.h>

int main(void) {
  printf("Hello World\n");
  return 0;
}
```

第一行是预处理信息，`#`表示是预处理指令，这里表示标准库`stdio.h`。注意，指令的尾部不需要分号表示结束。

第三行是主函数`main`，所有 C 程序都是从`main`开始运行，即自动调用`main`。这里的`main`函数返回整数`int`，参数是`void`，即无参数。

第四行是`printf`函数，用来将参数显示在屏幕上。注意，正常语句要用分号表示结束，这是因为正常语句可以写成多行，不用分号很难确定结束位置。而预处理指令都是一行的。

第五行是函数的返回值`0`，表示运行成功。如果运行失败，一般约定返回非零值。

然后，将这个源文件编译成可以运行的程序。

```bash
$ gcc hello.c
```

上面代码使用`gcc`编译器，将源文件`hello.c`编译成二进制代码。编译产物默认叫做`a.out`。执行这个文件，会输出`Hello World`。

```bash
$ ./a.out
Hello World
```

`-o`参数可以指定编译产物的文件名。

```bash
$ gcc -o hello hello.c
```

上面代码的编译产物就是`hello`。

```bash
$ ./hello
Hello World
```

## 注释

C 语言的注释用`/* .. comments .. */`表示，注释内部可以分行。

```c
/* comments */

/*
  This is a comment.
*/
```

C99 还支持双斜杠的`//`的单行注释。

```c
// This is a comment.
// This is another comment.
```

## 变量

变量名可以包括字母、数字和下划线，但是不能以数字开头。

声明变量的时候，需要提供类型。

```c
int num;
num = 42;
```

可以一次声明多个变量。

```c
float x, y, z, X;
```

注意，变量声明的时候，不会清空分配的内存，因此可能会得到任何值。

## 赋值运算符

赋值运算符`=`为变量赋值后，返回等号右边的值。

```c
y = (x = 2 * x)
```

上面代码中，变量`x`先是将自己的值倍增，然后返回这个新的值，赋给变量`y`。
