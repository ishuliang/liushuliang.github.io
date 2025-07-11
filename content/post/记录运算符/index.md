---
title: "运算符"
description: "常用运算符记录一下"
date: 2025-07-10T15:56:48+08:00
image: 0074dbe09767e97ac5e06f43b0d1586.jpg
slug: /20250710
categories: "knowledge"
---

# 运算符

# 编程语言中的运算符总览：按单目、双目、多目分类

运算符是编程语言的基础元素，用于构建表达式、实现运算和逻辑判断。本文以**运算符的元数（即操作数个数）**为主线，梳理常见的**单目（Unary）**、**双目（Binary）**和**多目（Ternary）**运算符。

---

## 一、单目运算符（Unary Operators）

单目运算符只需要一个操作数，常见如下：

| 运算符 | 含义说明              | 适用示例                  |
| ------ | --------------------- | ------------------------- |
| `+`    | 正号（通常可省略）    | `+a`                      |
| `-`    | 负号                  | `-a`                      |
| `++`   | 自增（前/后缀）       | `++a`, `a++` *(Java/C++)* |
| `--`   | 自减（前/后缀）       | `--a`, `a--` *(Java/C++)* |
| `!`    | 逻辑非                | `!flag`                   |
| `~`    | 位取反                | `~a`                      |
| `not`  | 布尔非                | `not a` *(Python)*        |
| `&`    | 引用/地址符（取地址） | `&x` *(C/C++)*            |
| `*`    | 指针解引用            | `*p` *(C/C++)*            |

`++`、`--`在数字前后是有区别的，在前表示先计算在赋值，在后表示先赋值再计算。

```
i = 100;

op1 = i++;  // op1 = 100，先 op1 = i，然后 i = i + 1

i = 100;

op2 = ++i;  // op2 = 101，先 i = i + 1，然后赋值 op2

i = 100;

op3 = i--;  // op3 = 100，先赋值 op3，然后 i = i - 1

i = 100;

op4 = --i;  // op4 = 99，先 i = i - 1，然后赋值 op4
```



---

## 二、双目运算符（Binary Operators）

双目运算符最为常见，涵盖算术、比较、逻辑等核心语义。

### 1. 算术运算符

| 运算符 | 含义     | 示例                |
| ------ | -------- | ------------------- |
| `+`    | 加法     | `a + b`             |
| `-`    | 减法     | `a - b`             |
| `*`    | 乘法     | `a * b`             |
| `/`    | 除法     | `a / b`             |
| `%`    | 取模     | `a % b`             |
| `**`   | 幂       | `a ** b` *(Python)* |
| `//`   | 地板除法 | `a // b` *(Python)* |

### 2. 赋值运算符

| 运算符 | 含义                                |
| ------ | ----------------------------------- |
| `=`    | 赋值                                |
| `+=`   | 加后赋值（`x += y` 即 `x = x + y`） |
| `-=`   | 减后赋值                            |
| `*=`   | 乘后赋值                            |
| `/=`   | 除后赋值                            |
| `%=`   | 取模赋值                            |
| `**=`  | 幂赋值                              |
| `//=`  | 整除赋值                            |

### 3. 比较运算符

| 运算符 | 含义                      |
| ------ | ------------------------- |
| `==`   | 相等                      |
| `!=`   | 不等                      |
| `>`    | 大于                      |
| `<`    | 小于                      |
| `>=`   | 大于等于                  |
| `<=`   | 小于等于                  |
| `is`   | 对象标识相等   *(Python)* |
| `in`   | 包含判断       *(Python)* |

### 4. 位运算符

| 运算符 | 含义                |
| ------ | ------------------- |
| `&`    | 位与                |
| `|`    | 位或                |
| `^`    | 位异或              |
| `<<`   | 左移                |
| `>>`   | 右移（算术）        |
| `>>>`  | 无符号右移 *(Java)* |

### 5. 逻辑运算符

| 运算符 | 含义                        |
| ------ | --------------------------- |
| `&&`   | 逻辑与（短路） *(Java/C++)* |
| `||`   | 逻辑或（短路）              |
| `and`  | 逻辑与 *(Python)*           |
| `or`   | 逻辑或 *(Python)*           |

---

## 三、多目运算符（Ternary Operators）

多目运算符中最经典的就是**条件（三元）运算符**：

| 运算符结构      | 含义                            | 示例           |
| --------------- | ------------------------------- | -------------- |
| `a ? b : c`     | 若 `a` 为真则为 `b`，否则为 `c` | *(Java/C/C++)* |
| `b if a else c` | 同上逻辑                        | *(Python)*     |

---

## 附录：其他运算符/结构（组合表达式）

- `,` 逗号运算符（C/C++ 中存在执行顺序控制）
- `->`、`.` 成员访问（结构体/对象）
- `::` 范围解析符（C++、Java 的静态成员访问）

---

## 总结

运算符数量虽不多，但掌握其分类和语义，可以帮助我们更好地理解表达式的构造与执行逻辑。建议在使用时牢记：

- **括号优先，避免歧义**
- **位运算性能好**
- **逻辑操作符优先考虑可读性和短路效应**