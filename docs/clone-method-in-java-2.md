# Java 中的 Clone()方法

> 原文:[https://www.geeksforgeeks.org/clone-method-in-java-2/](https://www.geeksforgeeks.org/clone-method-in-java-2/)

对象克隆是指创建对象的精确副本。它创建当前对象的类的新实例，并用该对象的相应字段的内容初始化它的所有字段。

**使用赋值运算符创建** **副本的** **参考变量**

在 Java 中，没有创建对象副本的操作符。与 C++不同，在 Java 中，如果我们使用赋值运算符，那么它将创建引用变量的副本，而不是对象的副本。这可以用一个例子来解释。下面的程序演示了相同的内容。

## 爪哇

T0】输出

```
10 20
100 20
100 20
```