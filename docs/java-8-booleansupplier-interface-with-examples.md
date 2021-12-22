# Java 8 | BooleanSupplier 接口示例

> 原文:[https://www . geesforgeks . org/Java-8-boolean supplier-interface-with-examples/](https://www.geeksforgeeks.org/java-8-booleansupplier-interface-with-examples/)

**BooleanSupplier 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个不接受任何参数但产生布尔值的函数。

分配给 BooleanSupplier 类型的对象的 lambda 表达式用于定义其**getasbolinan()**，该表达式最终对其参数应用给定的操作。这类似于使用类型为[供应商](https://www.geeksforgeeks.org/supplier-interface-in-java-with-examples/) <布尔>的对象

### boolean 供应商界面中的函数

BooleanSupplier 界面只包含一个功能:

### 1.getAsBoolean()

此方法不接受任何值，但会产生一个布尔结果。

**语法:**

```
boolean getAsBoolean()
```

**返回值:**该方法返回一个**布尔值**。

下面是说明 getAsBoolean()方法的代码:

**程序:**

```
// Java program to illustrate
// getAsBoolean() method of
// BooleanSupplier Interface

import java.util.function.BooleanSupplier;

public class GFG {
    public static void main(String args[])
    {

        // Create a BooleanSupplier instance
        BooleanSupplier sup = () -> true;

        // Get the boolean value
        // Using getAsBoolean() method
        System.out.println(sup.getAsBoolean());
    }
}
```

**输出:**

```
true

```