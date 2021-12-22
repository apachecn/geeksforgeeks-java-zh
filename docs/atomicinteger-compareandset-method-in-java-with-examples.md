# Java 中的 AtomicInteger compareAndSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicinteger-compareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-compareandset-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicnteger . compareandset()**是 Java 中的一个内置方法，如果当前值等于也在参数中传递的预期值，则将该值设置为参数中传递的值。该函数返回一个布尔值，它告诉我们更新是否完成。

**语法:**

> 公共最终布尔比较数据集(int expect，int val)

**参数:**该功能接受两个强制参数，如下所述:

*   **expect:** 指定原子对象应该是的值。
*   **val:** 指定原子整数等于期望值时要更新的值。

**返回值:**函数返回一个布尔值，成功则返回真，否则返回假。

下面的程序演示了该功能:

**程序 1:**

```
// Java Program to demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val = new AtomicInteger(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(0, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was"
                               + " updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出:**

```
Previous value: 0
The value was updated and it is 6

```

**程序二:**

```
// Java Program to demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res = val.compareAndSet(10, 6);

        // Checks if the value was updated.
        if (res)
            System.out.println("The value was"
                               + " updated and it is "
                               + val);
        else
            System.out.println("The value was "
                               + "not updated");
    }
}
```

**输出:**

```
Previous value: 0
The value was not updated

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicinteger . html # compareAndSet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#weakCompareAndSet--)