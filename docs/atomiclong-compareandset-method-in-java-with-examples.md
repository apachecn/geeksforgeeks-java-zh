# Java 中的 AtomicLong compareAndSet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-compareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-compareandset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomic clong . compareandset()**是 Java 中的一个内置方法，如果当前值等于也在参数中传递的预期值，则将该值设置为参数中传递的值。该函数返回一个布尔值，它告诉我们更新是否完成。

**语法:**

```java
public final boolean compareAndSet(long expect,
                                       long val)

```

**参数:**函数接受两个强制参数，描述如下:

*   **Expected:** Specifies the value that the atomic object should be.
*   **Val:** Specifies that the atomic integer is equal to the expected value to be updated.

**返回值:**函数返回一个布尔值，成功则返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(0, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was "
                               + "updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出:**

```java
Previous value: 0
The value was updated and it is 6

```

**程序二:**

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(10, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was "
                               + "updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出:**

```java
Previous value: 0
The value was not updated

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # compareAndSet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#weakCompareAndSet--)