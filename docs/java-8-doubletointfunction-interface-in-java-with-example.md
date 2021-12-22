# Java 8 | Java 中的 DoubleToIntFunction 接口，示例

> 原文:[https://www . geesforgeks . org/Java-8-double to function-Java 中的接口-带示例/](https://www.geeksforgeeks.org/java-8-doubletointfunction-interface-in-java-with-example/)

**double to function 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受双值参数并给出整型值结果的函数。

分配给 DoubleToIntFunction 类型的对象的 lambda 表达式用于定义其 **applyAsInt()** ，该表达式最终对其唯一的参数应用给定的操作。这类似于使用类型为函数<双精度，整数>的对象。

DoubleToIntFunction 接口只有一个功能:

**applyAsInt()** :这个方法接受一个双值参数并给出一个 Int 值结果。

**语法:**

```java
int applyAsInt(double value)
```

**参数:**该方法接受一个参数**值**，该值是作为整数应用的双值参数。

**返回:**该方法返回一个**整数值**结果。

下面是说明 applyAsInt()方法的代码:

**程序**

```java
// Java Program to demonstrate
// DoubleToIntFunction's applyAsInt() method

import java.util.function.DoubleToIntFunction;

public class Main {
    public static void main(String args[])
    {

        // Create a DoubleToIntFunction
        DoubleToIntFunction truncate = a -> (int)a;

        // Apply the function using applyAsInt()
        System.out.println(truncate.applyAsInt(10.6));
    }
}
```

**输出:**

```java
10

```