---
title: 剪切，复制，粘贴
date: 2016-11-30
author: 阮一峰
---

## 剪切

`d`命令不仅删除文本，它还“剪切”文本。每次我们使用`d`命令，删除的部分被复制到一个粘贴缓冲区中（看作剪切板）。

## 粘贴

- `p`命令 剪切板中的文本粘贴到光标位置之后。
- `P` 剪切板中的文本粘贴到光标之前。
- `:r` 把指定的文件插入到光标位置之前

```
:r foo.txt
```

## 复制

- yy	复制当前行。
- 5yy	复制当前行及随后的四行文本。
- yW	复制从当前光标位置到下一个单词的开头。
- y$	复制从当前光标位置到当前行的末尾。
- y0	复制从当前光标位置到行首。
- y^	复制从当前光标位置到文本行的第一个非空字符。
- yG	复制从当前行到文件末尾。
- y20G	复制从当前行到文件的第20行。
