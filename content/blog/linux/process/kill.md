---
title: 终止进程
date: 2017-09-24
author: 阮一峰
---

## 概述

如果进程失去响应，这时可以手动终止该进程。

`kill`和`killall`是清除进程的两个命令。它们的区别是，`killall`根据名称终止进程，`kill`根据进程号（PID）终止进程。注意，用户只能终止自己的进程，不能终止属于其他用户的进程，根用户可以终止所有进程。

这两个命令会通过内核，向指定的进程发送信号。常用的是以下三个信号。

- 1 （-HUP）：重启一个进程。
- 9 （-KILL）：要求进程自己终止。
- 15 （-TERM）：强制终止进程。

不指定信号时，`kill`和`killall`默认发送信号`15`。

有三种方式可以指定信号。

- 使用数字（例如`-1`）
- 使用`SIG`前缀 + 信号名（例如`-SIGHUP`）
- 使用信号名（例如`-HUP`）

以下命令可以列出所有信号。

```bash
$ kill -l
# 或者
$ killall -l
```

## kill 命令

下面是`kill`命令的用法例子。

```bash
# 终止单个进程
$ kill -9 2551

# 终止多个进程
$ kill -9 2551 2514 1963 1856 1771
```

## killall 命令

`killall`命令终止与指定名称匹配的所有进程。

```bash
# 终止所有与 chrome 匹配的进程
$ killall -9 chrome
```

`killall`命令也可以终止某个用户的所有进程。

```bash
# 终止用户 sara 的所有进程
$ killall -u sara
```

`-g`参数表示终止属于某个用户组的进程。

```bash
$ kill -e -g root apache2
```

`-v`和`--verbose`表示详细输出操作过程。

```bash
$ sudo killall -v fail2ban-server
Killed fail2ban-server(19099) with signal 15
```

## pkill 命令

`pkill`命令用来终止符合指定条件的所有进程。

`-e`参数代表`echo`，表示输出操作结果。

```bash
$ pkill -e mysql
```

`-u`参数可以指定只终止属于某个用户的进程。

```bash
$ sudo pkill -e -u root apache2
```

