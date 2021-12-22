# Java 中的 LongFunction 接口，示例

> 原文:[https://www . geesforgeks . org/long function-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/longfunction-interface-in-java-with-examples/)

**LongFunction Interface** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受长值参数并产生类型为 **R** 的结果的函数。

该功能界面只接受一个泛型，即:-

*   **r** : indicates the type of output of this function.

分配给 LongFunction 类型的对象的 lambda 表达式用于定义其 **apply()** ，该表达式最终将给定的操作应用于其唯一的参数。类似于使用[功能](https://www.geeksforgeeks.org/function-interface-in-java-with-examples/) <龙、R >类型的物体。

LongFunction 界面只有一个功能:

### 应用()

此方法接受长值参数，并给出 r 类型的结果

**语法:**

```
R apply(long value)
```

**参数:**此方法接受一个参数**值**，这是一个长值参数。

**返回:**该方法返回类型为 **R** 的值。

下面是说明 apply()方法的代码:

**程序**

```
import java.util.function.LongFunction;

public class Main {
    public static void main(String args[])
    {

        LongFunction<Double> ob = a -> a / 2.0;

        // Using apply()
        System.out.println(ob.apply(3));
    }
}
```

**输出:**

```
1.5

```