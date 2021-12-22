# Java 8 |双供应商界面示例

> 原文:[https://www . geesforgeks . org/Java-8-double supplier-interface-with-examples/](https://www.geeksforgeeks.org/java-8-doublesupplier-interface-with-examples/)

**双供应商接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个不接受任何参数但产生一个双精度值的函数。

分配给 DoubleSupplier 类型的对象的 lambda 表达式用于定义其 **getAsDouble()** ，该表达式最终对其参数应用给定的操作。类似于使用[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/) <双>类型的对象

### 双供应商界面中的功能

双供应商界面只有一个功能:

### 1.getAsDouble()

此方法不接受任何值，但会产生一个双值结果。

**语法:**

```
double getAsDouble()
```

**返回值:**该方法返回**一个双精度值。**

下面是演示 getAsDouble()方法的代码:

**程序:**

```
// Java Program to illustrate
// getAsDouble method of
// DoubleSupplier Interface
import java.util.function.DoubleSupplier;

public class GFG {
    public static void main(String args[])
    {

        // Create a DoubleSupplier instance
        DoubleSupplier sup = () -> Math.random();

        // Get the double value
        // Using getAsDouble() method
        System.out.println(sup.getAsDouble());
    }
}
```

**输出:**

```
0.10283070415816953

```