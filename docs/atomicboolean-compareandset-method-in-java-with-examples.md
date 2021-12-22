# Java 中的 AtomicBoolean compareAndSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-compareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-compareandset-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicboolean . compareandset()**是 Java 中的一个内置方法，如果当前值等于也在参数中传递的预期值，则将该值设置为参数中传递的值。该函数返回一个布尔值，它告诉我们更新是否完成。

**语法:**

> 公共最终布尔比较数据集(布尔期望，布尔值)

**参数:**该功能接受两个强制参数，如下所述:

*   **expect:** 指定原子对象应该是的值。
*   **val:** 指定如果原子布尔值等于预期值，将更新的值。

**返回值:**函数返回一个布尔值，成功则返回真，否则返回假。

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val = new AtomicBoolean(false);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was false
        // and then updates it
        boolean res = val.compareAndSet(false, true);

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

```java
Previous value: false
The value was updated and it is true

```

**程序二:**

```java
// Java Program to demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val = new AtomicBoolean(true);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was true
        // and then updates it
        boolean res = val.compareAndSet(true, false);

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

```java
Previous value: true
The value was updated and it is false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicboolean . html # compareAndSet(布尔值，% 20 布尔值)](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicBoolean.html#compareAndSet(boolean, %20boolean))