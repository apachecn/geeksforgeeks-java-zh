# Java 中的 LongToIntFunction 接口，示例

> 原文:[https://www . geesforgeks . org/longpointfunction-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/longtointfunction-interface-in-java-with-examples/)

**longpointfunction 接口**是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受长值参数并给出整型值结果的函数。

分配给 DoubleToLongFunction 类型的对象的 lambda 表达式用于定义其 **applyAsInt()** ，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为[函数](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/) <长整型>的对象。

LongToIntFunction 接口只有一个功能:

### applyAsInt()

此方法接受长值参数并给出一个整型值结果。

**语法:**

```
int applyAsInt(long value)
```

**参数:**此方法接受一个参数**值**，这是长值参数。

**返回:**该方法返回一个**整数值**结果。

下面是说明 applyAsInt()方法的代码:

**程序**

```
// Java Program to demonstrate
// LongToIntFunction's applyAsInt() method

import java.util.function.LongToIntFunction;

public class Main {
    public static void main(String args[])
    {

        // Instantiating LongToIntFunction
        LongToIntFunction ob = a -> (int)a * 100000;

        // Applying the above function
        // using applyAsInt()
        System.out.println(ob.applyAsInt(2));
    }
}
```

**输出:**

```
200000

```