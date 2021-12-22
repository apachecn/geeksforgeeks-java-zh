# Java 中的 AtomicInteger updateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-updateandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-updateandget-method-in-java-with-examples/)

**Java。atomicinteger . updateandget()**方法是一个内置方法，通过对当前值应用指定的操作来更新对象的当前值。它以[输入操作器](https://www.geeksforgeeks.org/intunaryoperator-interface-in-java/)界面的一个对象为参数，并将该对象中指定的操作应用于当前值。它返回更新后的值。

**语法:**

```java
public final int updateAndGet(IntUnaryOperator function)

```

**参数:**该方法接受[输入操作器](https://www.geeksforgeeks.org/intunaryoperator-interface-in-java/)T4 功能作为参数。
将给定的函数应用于对象的当前值。

**返回值:**函数返回当前对象的更新值。

**举例说明功能。**

**程序 1:**

```java
// Java program to demonstrate the above function

import java.util.concurrent.atomic.AtomicInteger;
import java.util.function.IntUnaryOperator;

public class Demo {
    public static void main(String[] args)
    {

        // Atomic Integer initialized with a value of 10
        AtomicInteger ai = new AtomicInteger(10);

        // Unary operator defined to negate the value
        IntUnaryOperator unaryOperator = (x) -> - x;

        System.out.println("Initial Value is " + ai);

        // Function called and the unary operator
        // is passed as an argument
        int x = ai.updateAndGet(unaryOperator);
        System.out.println("Updated value is " + x);
    }
}
```

**Output:**

```java
Initial Value is 10
Updated value is -10

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html)