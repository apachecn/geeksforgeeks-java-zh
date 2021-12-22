# Java 中的双消费者接口，示例

> 原文:[https://www . geesforgeks . org/double consumer-in-Java-interface-with-examples/](https://www.geeksforgeeks.org/doubleconsumer-interface-in-java-with-examples/)

**双消费者接口**是 **java.util.function** 包的一部分，该包是从 java 8 开始引入的，用于在 Java 中实现[函数编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受一个双值参数但不返回值的函数。

分配给 DoubleConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为[消费者](https://www.geeksforgeeks.org/java-8-consumer-interface-in-java-with-examples/) <双>的对象

双消费者界面由以下两个功能组成:

### 接受()

此方法接受一个值，并对其唯一的参数执行操作。

**语法:**

```
void accept(double value)
```

**参数:**该方法只接受一个参数:

*   **值**–输入参数

**返回:**该方法不返回值。

下面是说明 accept()方法的代码:

```
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a DoubleConsimer Instance
        DoubleConsumer
            display
            = a -> System.out.println(a * 10);

        // using accept() method
        display.accept(3);
    }
}
```

**Output:**

```
30.0

```

### 然后()

它返回一个复合双消费者，其中参数化双消费者将在第一个双消费者之后执行。如果任一操作的计算引发错误，它将被中继到合成操作的调用方。

**注意:**作为参数传递的操作应为 DoubleConsumer 类型。

**语法:**

```
default DoubleConsumer andThen(DoubleConsumer after)
```

**参数:**该方法接受之后的参数**，该参数是当前参数之后要应用的双消费者。**

**返回值:**这个方法返回一个复合的 DoubleConsumer，首先应用当前操作，然后应用后操作。

**异常:**如果后操作为空，该方法抛出**空指针异常**。

下面是说明 andThen()方法的代码:

**程序 1:**

```
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a DoubleConsimer Instance
        DoubleConsumer display = a -> System.out.println(a * 10);
        DoubleConsumer mul = a -> a /= 2;

        // using addThen() method
        DoubleConsumer composite = mul.andThen(display);
        composite.accept(3);
    }
}
```

**Output:**

```
30.0

```

**程序 2:** 演示**空指针异常**何时返回。

```
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a DoubleConsimer Instance
        DoubleConsumer mul = a -> a /= 10;

        try {

            // using addThen() method
            DoubleConsumer composite = mul.andThen(null);

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
import java.util.function.DoubleConsumer;

public class GFG {
    public static void main(String args[])
    {

        try {

            DoubleConsumer
                conv
                = a
                -> System.out.println(
                    Integer
                        .parseInt(
                            Double
                                .toString(a)));
            DoubleConsumer mul = a -> a /= 10;

            // using addThen() method
            DoubleConsumer composite = mul.andThen(conv);

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
Exception : java.lang.NumberFormatException: For input string: "3.0"

```