# Java 8 |带示例的长供应商界面

> 原文:[https://www . geesforgeks . org/Java-8-longsupplier-interface-with-examples/](https://www.geeksforgeeks.org/java-8-longsupplier-interface-with-examples/)

**LongSupplier 接口**是 **java.util.function** 包的一部分，该包是从 java 8 开始引入的，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它代表一个不接受任何参数但产生一个长值的函数。

分配给 LongSupplier 类型的对象的 lambda 表达式用于定义其**getallong()**，该表达式最终对其参数应用给定的操作。类似于使用[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/) <龙>类型的物件

### 长供应商界面中的功能

长供应商界面只有一个功能:

### 1.getAsLong()

此方法不接受任何值，但会产生长值结果。

**语法:**

```java
long getAsLong()
```

**返回值:**该方法返回**一个长值。**

下面是说明 getAsLong()方法的代码:

**程序:**

```java
// Java program to illustrate
// getAsLong() method

import java.util.function.LongSupplier;

public class GFG {
    public static void main(String args[])
    {

        // Create a LongSupplier instance
        LongSupplier
            sup
            = () -> (int)(Math.random() * 10);

        // Get the long value
        // Using getAsLong() method
        System.out.println(sup.getAsLong());
    }
}
```

**输出:**

```java
6

```