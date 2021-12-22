# Java 中的 AtomicLong accumulateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomiclong-accumulatedget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-accumulateandget-method-in-java-with-examples/)

**Java。atomiclong . accumulatedget()**方法是一个内置方法，它通过对当前值和作为参数传递的值应用指定的操作来更新对象的当前值。它将一个 long 作为其参数和 LongBinaryOperator 接口的一个对象，并将该对象中指定的操作应用于这些值。它返回更新后的值。

**语法:**

```java
public final long accumulateAndGet(long y, 
              LongBinaryOperator function)
```

**参数:**该方法接受一个长值 **y** 和一个长边操作符**函数**作为参数。它将给定的函数应用于对象的当前值和值 y。

**返回值:**函数返回当前对象的更新值。

**举例说明功能。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicLong accumulateAndGet() method

import java.util.concurrent.atomic.AtomicLong;
import java.util.function.LongBinaryOperator;

public class Demo {
    public static void main(String[] args)
    {
        // AtomicLong initialized with a value of 555
        AtomicLong atomicLong = new AtomicLong(555);

        // Binary operator defined
        // to calculate the product
        LongBinaryOperator binaryOperator
            = (x, y) -> x * y;

        System.out.println("Initial Value is "
                           + atomicLong);

        // Function called and the binary operator
        // is passed as an argument
        long value
            = atomicLong
                  .accumulateAndGet(555, binaryOperator);
        System.out.println("Updated value is "
                           + value);
    }
}
```

**Output:** 

```java
Initial Value is 555
Updated value is 308025
```

**参考:**T2T4】