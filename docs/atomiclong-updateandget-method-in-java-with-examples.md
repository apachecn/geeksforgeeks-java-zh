# Java 中的 AtomicLong updateAndGet()方法，示例

> 原文:[https://www . geesforgeks . org/atomiclong-updateandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-updateandget-method-in-java-with-examples/)

**Java。AtomicLong.updateAndGet()** 方法是一个内置方法，通过对当前值应用指定的操作来更新对象的当前值。它以[longunaryooperator](https://www.geeksforgeeks.org/longunaryoperator-interface-in-java/)界面的一个对象为参数，将该对象中指定的操作应用于当前值。它返回更新后的值。

**语法:**

```
public final long updateAndGet(LongUnaryOperator function)
```

**参数:**该方法接受[长月运算器](https://www.geeksforgeeks.org/longunaryoperator-interface-in-java/)T4 功能作为参数。它将给定的函数应用于对象的当前值。

**返回值:**函数返回当前对象的更新值。

**举例说明功能。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// AtomicLong updateAndGet() method

import java.util.concurrent.atomic.AtomicLong;
import java.util.function.LongUnaryOperator;

public class Demo {
    public static void main(String[] args)
    {
        // AtomicLong initialized with a value of -20000
        AtomicLong al = new AtomicLong(-20000);

        // Unary operator defined to negate the value
        LongUnaryOperator unaryOperator = (x) -> - x;

        System.out.println("Initial Value is " + al);

        // Function called and the unary operator
        // is passed as an argument
        long x = al.updateAndGet(unaryOperator);
        System.out.println("Updated value is " + x);
    }
}
```

**Output:** 

```
Initial Value is -20000
Updated value is 20000
```

**参考:**T2T4】