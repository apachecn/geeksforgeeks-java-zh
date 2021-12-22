# 通过 Java 中的参数化和规范进行抽象

> 原文:[https://www . geeksforgeeks . org/通过参数化和规范抽象 java/](https://www.geeksforgeeks.org/abstraction-by-parameterization-and-specification-in-java/)

参数化抽象和规范抽象都是 Java 中的重要方法。我们这样做是希望通过将属性和用户需求的细节实现分开来简化我们的分析，方法是向用户显示基本部分，并隐藏某些细节以用于各种目的，如安全性、维护等。

*   Abstraction helps us in many ways, just like a simple way to arrange code.
*   It also helps to break down big steps into small steps.
*   Used to suppress details and simplify interaction.
*   Abstract plays an important role in improving the maintenance part of the project.

**示例:**

基本上，抽象是一种通过隐藏所有机制来提供简单性的方法。例如，当有人打电话给你时，你会在屏幕上看到 xyz 在打电话给你，绿色图标表示要接收，红色图标表示拒绝选项和一些消息传递选项，但是你没有看到的是所有的后端机制，即某人如何打电话给你，通过点击屏幕上的图标，你可以接收/拒绝或向某人发送短信，告诉他它将如何连接到呼叫者所有的东西。这种抽象方式使事情变得简单。

## 爪哇

T0T6】

**输出:**

```
Fee :1000
Hello! Ashish your roll_no is :12345

```

**抽象方法:**

*   Parameterized abstraction.
*   Abstract according to specifications.

**参数化提取:**

它通过用参数替换数据的身份来提取数据。

**示例–**

```
x % 2  =  0

```

它描述了一个计算，当我们把一个数 x 除以 2，余数等于零，我们用它来发现给定的数 x 是偶数还是不是。

```
x : int(x % 2 == 0)(y)

```

其含义与

```
y % 2==0

```

相同

在更熟悉的符号中，我们可以用下面给出的表达式来表示前面的表达式。

## 爪哇

T5

```
class Abstraction {

    // Abstraction by parameterization
    int Even(int x)
    {
        if (x % 2 == 0)
            return x;
    }
}
```