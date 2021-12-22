# Java 中的 atomic reference getAndAccumulate()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomic reference-getandaccumulate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-getandaccumulate-method-in-java-with-examples/)

**原子引用**类的 **getAndAccumulate()** 方法用于自动更新原子引用的当前值，将给定的累积函数应用于当前值和给定值，并返回前一个值。累积函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可以被重新应用。应用函数时，当前值作为其第一个参数，给定的更新作为第二个参数。
**语法:**

```java
public final E getAndAccumulate(E x,
     BinaryOperator<E> accumulatorFunction)
```

**参数:**此方法接受:

*   **x** 是更新后的值
*   **累积函数**是两个自变量的无副作用函数。

**返回值:**此方法返回**之前的值**。
下面的程序说明了 getAndAccumulate()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.getAndAccumulate() method

import java.util.concurrent.atomic.*;
import java.util.function.BinaryOperator;

public class GFG {
    public static void main(String args[])
    {

        // AtomicReference with value
        AtomicReference<Integer> ref
            = new AtomicReference<>(3456);

        // Value to apply getAndAccumulate
        int x = 45654;

        // Declaring the accumulatorFunction
        // applying function to add value as string
        BinaryOperator add
            = (u, v) -> u.toString() + v.toString();

        // apply getAndAccumulate()
        int value = ref.getAndAccumulate(x, add);

        // print AtomicReference
        System.out.println(
            "The AtomicReference previous value: "
            + value);
        System.out.println(
            "The AtomicReference new value: "
            + ref.get());
    }
}
```

**Output:**