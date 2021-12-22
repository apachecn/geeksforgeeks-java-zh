# Java 中的 LongConsumer 接口，示例

> 原文:[https://www . geesforgeks . org/long consumer-interface-in-Java-with-examples/](https://www.geeksforgeeks.org/longconsumer-interface-in-java-with-examples/)

**LongConsumer Interface** 是从 java 8 开始引入的 **java.util.function** 包的一部分，用于在 Java 中实现[函数式编程](https://www.geeksforgeeks.org/functional-programming-paradigm/)。它表示一个接受一个长值参数但不返回值的函数。

分配给 LongConsumer 类型的对象的 lambda 表达式用于定义其 **accept()** ，该表达式最终将给定的操作应用于其唯一的参数。这类似于使用类型为[消费者](https://www.geeksforgeeks.org/java-8-consumer-interface-in-java-with-examples/) <龙>的对象

LongConsumer 界面由以下两个功能组成:

### 接受()

此方法接受一个值，并对其唯一的参数执行操作。

**语法:**

```java
void accept(long value)
```

**参数:**该方法只接受一个参数:

*   **值**–输入参数

**返回:**该方法不返回值。

下面是说明 accept()方法的代码:

```java
import java.util.function.LongConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a LongConsimer Instance
        LongConsumer
            display
            = a -> System.out.println(a * 100);

        // Using accept() method
        display.accept(3);
    }
}
```

**Output:**

```java
300

```

### 然后()

它返回一个合成的 LongConsumer，其中参数化的 LongConsumer 将在第一个之后执行。如果任一操作的计算引发错误，它将被中继到合成操作的调用方。

**注意:**作为参数传递的操作应为 LongConsumer 类型。

**语法:**

```java
default LongConsumer andThen(LongConsumer after)
```

**参数:**该方法接受之后的参数**，该参数是当前参数之后要应用的 LongConsumer。**

**返回值:**该方法返回一个组合 LongConsumer，首先应用当前操作，然后应用后操作。

**异常:**如果后操作为空，该方法抛出**空指针异常**。

下面的程序说明了 andThen()方法:

**程序 1:**

```java
import java.util.function.LongConsumer;

public class GFG {
    public static void main(String args[])
    {

        // Create a LongConsimer Instance
        LongConsumer
            display
            = a -> System.out.println(a * 10);
        LongConsumer mul = a -> a *= 100;

        // Using addThen() method
        LongConsumer composite = mul.andThen(display);

        composite.accept(3);
    }
}
```

**Output:**

```java
30

```

**程序 2:** 演示**空指针异常**何时返回。

```java
import java.util.function.LongConsumer;

public class GFG {
    public static void main(String args[])
    {

        try {

            LongConsumer mul = a -> a *= 10;
            LongConsumer composite = mul.andThen(null);
            composite.accept(3);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.NullPointerException

```

**程序 3:** 演示 after 函数中的异常是如何返回和处理的。

```java
import java.util.function.LongConsumer;

public class GFG {
    public static void main(String args[])
    {

        try {
            LongConsumer divide = a -> a = a / (a - 3);
            LongConsumer mul = a -> a *= 10;
            LongConsumer composite = mul.andThen(divide);
            composite.accept(3);
        }
        catch (Exception e) {
            System.out.println("Exception : " + e);
        }
    }
}
```

**Output:**

```java
Exception : java.lang.ArithmeticException: / by zero

```