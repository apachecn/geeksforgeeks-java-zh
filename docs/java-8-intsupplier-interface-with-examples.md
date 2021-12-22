# Java 8 |带示例的 IntSupplier 接口

> 原文:[https://www . geesforgeks . org/Java-8-int supplier-interface-with-examples/](https://www.geeksforgeeks.org/java-8-intsupplier-interface-with-examples/)

**IntSupplier Interface** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个不接受任何参数但产生一个 int 值的函数。

分配给 IntSupplier 类型的对象的 lambda 表达式用于定义其 **getAsInt()** ，该表达式最终对其参数应用给定的操作。类似于使用[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/) <整数>类型的对象

### 供应商接口中的功能

IntSupplier 界面只包含一个功能:

### 1.getAsInt()

这个方法不接受任何值，但是产生一个整型值的结果。

**语法:**

```
int getAsInt()
```

**返回值:**该方法返回**一个整数值**。

下面是演示 getAsInt()方法的代码:

**程序:**

```
// Java program to illustrate
// getAsInt method of IntSupplier Interface

import java.util.function.IntSupplier;

public class GFG {
    public static void main(String args[])
    {

        // Create a IntSupplier instance
        IntSupplier
            sup
            = () -> (int)(Math.random() * 10);

        // Get the int value
        // Using getAsInt() method
        System.out.println(sup.getAsInt());
    }
}
```

**输出:**

```
7

```