# Java 中的 IntConsumer 接口，示例

> 原文:[https://www . geesforgeks . org/int consumer-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/intconsumer-interface-in-java-with-examples/)

**IntConsumer Interface** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受一个整数值参数但不返回值的函数。

分配给 IntConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为[消费者](https://www.geeksforgeeks.org/java-8-consumer-interface-in-java-with-examples/) <整数>的对象

IntConsumer 界面由以下两个功能组成:

### 接受()

此方法接受一个值，并对其唯一的参数执行操作。

**语法:**

```
void accept(int value)
```

**参数:**该方法只接受一个参数:

*   **值**–输入参数

**返回:**该方法不返回值。

下面是说明 accept()方法的代码:

```
import java.util.function.IntConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a IntConsimer Instance
        IntConsumer display = a -> System.out.println(a * 10);

        // Using accept() method
        display.accept(3);
    }
}
```

**Output:**

```
30

```

### 然后()

它返回一个合成的 IntConsumer，其中参数化的 IntConsumer 将在第一个之后执行。如果任一操作的计算引发错误，它将被中继到合成操作的调用方。

**注意:**作为参数传递的操作应为 IntConsumer 类型。

**语法:**

```
default IntConsumer andThen(IntConsumer after)
```

**参数:**该方法接受之后的参数**，该参数是当前参数之后要应用的 IntConsumer。**

**返回值:**这个方法返回一个复合的 IntConsumer，首先应用当前操作，然后应用后操作。

**异常:**如果后操作为空，该方法抛出**空指针异常**。

下面的程序说明了 andThen()方法:

**程序 1:**

```
import java.util.function.IntConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a IntConsimer Instance
        IntConsumer display = a -> System.out.println(a * 10);
        IntConsumer mul = a -> a *= 10;

        // Using andThen() method
        IntConsumer composite = mul.andThen(display);
        composite.accept(3);
    }
}
```

**Output:**

```
30

```

**程序 2:** 演示**空指针异常**何时返回。

```
import java.util.function.IntConsumer;

public class GFG {
    public static void main(String args[])
    {

        try {

            // Create a IntConsimer Instance
            IntConsumer mul = a -> a *= 10;
            IntConsumer composite = mul.andThen(null);
            composite.accept(3);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.NullPointerException

```

**程序 3:** 演示 after 函数中的异常是如何返回和处理的。

```
import java.util.function.IntConsumer;

public class GFG {
    public static void main(String args[])
    {

        try {
            // Create a IntConsimer Instance
            IntConsumer divide = a -> a = a / (a - 3);
            IntConsumer mul = a -> a *= 10;
            IntConsumer composite = mul.andThen(divide);
            composite.accept(3);
        }

        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```
Exception : java.lang.ArithmeticException: / by zero

```