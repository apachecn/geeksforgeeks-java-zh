# Java 8 | Java 中的 DoubleToLongFunction 接口，带示例

> 原文:[https://www . geesforgeks . org/Java-8-double to long function-Java 中的接口-示例/](https://www.geeksforgeeks.org/java-8-doubletolongfunction-interface-in-java-with-examples/)

**DoubleToLongFunction 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示接受双值参数并给出长值结果的函数。

分配给 DoubleToLongFunction 类型的对象的 lambda 表达式用于定义其 **applyAsLong()** ，该表达式最终将给定的操作应用于其唯一的参数。类似于使用【功能】双，龙>类型的对象。

DoubleToLongFunction 接口只有一个功能:

**1。applyAsLong() :** 此方法接受双值参数并给出长值结果。

**语法:**

```java
long applyAsLong(double value)
```

**参数:**该方法取一个参数**值**，为双值自变量。

**返回:**该方法返回一个**长值**结果。

下面是说明 applyAsLong()方法的代码:

**程序**

```java
// Java Program to demonstrate
// DoubleToLongFunction's applyAsLong() method

import java.util.function.DoubleToLongFunction;

public class Main {
    public static void main(String args[])
    {

        // Declare the DoubleToLongFunction
        DoubleToLongFunction truncate = a -> (long)a;

        // Apply the function to get the result as long
        // using applyAsLong()
        System.out.println(truncate.applyAsLong(10.6));
    }
}
```

**输出:**

```java
10

```