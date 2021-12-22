# 用示例在 Java 中原子克隆 getAndUpdate()方法

> 原文:[https://www . geesforgeks . org/atomiclong-getandupdate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-getandupdate-method-in-java-with-examples/)

**Java。AtomicLong.getAndUpdate()** 方法是一个内置方法，通过对当前值应用指定的操作来更新对象的当前值。它以[longunaryooperator](https://www.geeksforgeeks.org/longunaryoperator-interface-in-java/)界面的一个对象为参数，将该对象中指定的操作应用于当前值。它返回前一个值。

**语法:**

```java
public final long getAndUpdate(LongUnaryOperator function)

```

**参数:**该方法接受一个 LongUnaryOperator **函数**作为参数。
它将给定的函数应用于对象的当前值。

**返回值:**函数返回对象的前一个值。

**举例说明功能。**

```java
import java.util.concurrent.atomic.AtomicLong;
import java.util.function.LongUnaryOperator;

public class Demo {
    public static void main(String[] args)
    {
        // AtomicLong initialized with a value of -20000
        AtomicLong al = new AtomicLong(-20000);

        // Unary operator defined to negate the value
        LongUnaryOperator unaryOperator = (x) -> - x;

        // Function called and the unary operator
        // is passed as an argument
        long x = al.getAndUpdate(unaryOperator);
        System.out.println("Previous value is " + x);
        System.out.println("Updated Value is " + al);
    }
}
```

**Output:**

```java
Previous Value is -20000
Updated value is 20000

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html)