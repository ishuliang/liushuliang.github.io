---
title: "正则表达式学习"
description: 简单学了一下正则表达式，记一下字符用法。
date: 2025-06-23T16:39:04+08:00
image: 20250623.jpg
slug: /20250623
categories: "knowledge"
---

# 正则表达式



## 基本匹配

我们想要查找的字符或单词可以直接输入，就像搜索一样。例如，要找出文本中的 curious 一词，只需输入同样的内容。

### 任何字符

点`.`：允许匹配任何字符，包括特殊字符和空格

### 字符集`[abc]`

如果一个词中的字符可以是各种字符，我们就将所有的可选字符写进中括号 [] 中。例如，为了查找文本中的所有单词，我们需要编写表达式，在 [] 中相邻地输入字符 a、e、i、o、u。

### 否定字符集`[^abc]`

为了查找下方文本的所有单词（`ber` 和`bor` 除外），请在 [] 中的 ^ 后面并排输入 e 和 o。

### 字母范围`[a-z]`

为了查找指定范围的字母，我们需要将起始字母和结束字母写进 `[] `中，中间用连字符`-`分隔。它区分大小写。请编写表达式，匹配`e`和`o`之间所有的小写字母，包括它们本身。

### 数字范围`[0-9]`

为了查找指定范围的数字，我们需要在`[]`中输入起始和结束数字，中间用连字符`-`分隔。请编写表达式，匹配`3`到`6`之间的所有数字，包括它们本身。

## 重复

一些特殊字符用来指定一个字符在文本中重复的次数。它们分别是加号`+`、星号`*`和问号`?`。

### 星号`*`

在字符后面加上`*`，表示一个字符没有或者存在多次。

### 加号`+`

在字符后面加上`+`，表示一个字符出现一次或者多次

### 问号`?`

在字符后面加上`+`，表示一个字符可选，出现一次或者一次都没有

### 大括号-1

用`{n}`编写表达式，匹配文本中位数为n的字符。

### 大括号-2

用`{n,}`编写表达式，匹配文本中位数至少为n的字符。

### 大括号-3

用`{n,m}`编写表达式，匹配文本中位数为n至m的字符。

## 分组

我们可以对一个表达式进行分组，并用这些分组来引用或执行一些规则。

### 括号`()`分组

使用括号包裹字符，实现分组

### 引用组

使用`\1`来避免重复书写，这里1表示分组顺序。

### 非捕获分组

使用括号`(?:)`分组，确保它不会被引用捕获。

## 特殊字符

### 竖线`|`

竖线允许一个表达式包含多个不同的分支。所有分支用`|`分隔。和在字符层面上运作的字符集`[abc]`不同，分支在表达式层面上运作。

### 转义字符`\`

在书写正则表达式时，我们会用到`{}[]\/+*.$^|?`这些特殊字符。为了匹配这些特殊字符本身，我们需要使用`\`进行转义。

### 插入符`^`

匹配字符串的开始。如果仅仅需要查找行首字符，就在表达式前面添加`^`。

### 美元符号`$`

匹配字符串的结束。加在字符的后面。

## 单词字符

### `\w`

匹配字母、数字、下划线。

### `\W`

匹配除字母、数字、下划线之外的字符。

### 数字符`\d`

仅匹配数字。

### 非数字符`\D`

匹配除数字外的所有字符。

### 空白符`\s`

仅匹配空白字符。

### 非空白符`\S`

匹配除空白符之外的字符。

## 零宽断言

如果我们希望正在写的词语出现在另一个词语之前或之后，我们需要使用零宽断言。

### 正向先行断言`(?=)`

为了匹配后面有指定字符的值，我们可以在=后面写。放在字符后

### 负向先行断言`(?!)`

为了匹配后面没有有指定字符的值，我们可以在!后面写。

### 正向后行断言`(?<=)`

为了匹配前面有指定字符的值，我们可以在=后面写。放在字符前

### 负向后行断言`(?<!)`

为了匹配前面没有指定字符的值，我们可以在!后面写。

## 标志

标志改变表达式的输出。这就是标志也称为`修饰符`的原因。标志决定表达式是否将文本视作单独的行处理，是否区分大小写，或者是否查找所有匹配项。

### 全局标志`g`

表达式以`//`包裹，在后面加g表示匹配全局符合要求的，否则只有一个匹配项。

### 多行标志`m`

正则表达式将所有文本视作一行。但如果我们使用了多行标志，它就会单独处理每一行。

### 忽略大小写标志`i`

为了使我们编写的表达式不再大小写敏感，我们必须启用`不区分大小写`标志。

### 贪婪匹配

正则表达式默认执行贪婪匹配。这意味着匹配内容会尽可能长。

### 懒惰匹配

与贪婪匹配不同，懒惰匹配在第一次匹配时停止。