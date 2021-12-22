# Java 中的 AtomicLong weakCompareAndSet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-weakcompareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-weakcompareandset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomic clong . WeakCompareandset()**是 Java 中的一个内置方法，如果当前值等于也在参数中传递的预期值，则将该值设置为参数中传递的值。该函数返回一个布尔值，它告诉我们更新是否完成。

**语法:**

```
public final boolean weakCompareAndSet(long expect,
                                       long val)
```

**参数:**该功能接受两个强制参数，如下所述:

*   **expect:** 指定原子对象应该是的值。
*   **val:** 指定当原子长度等于预期时要更新的值。

**返回值:**函数返回一个布尔值，成功则返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program that demonstrates
// the weakCompareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prlongs the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res
            = val.weakCompareAndSet(0, 6);

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

**Output:** 

```
Previous value: 0
The value was updated and it is 6
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program that demonstrates
// the weakCompareAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Prlongs the updated value
        System.out.println("Previous value: "
                           + val);

        // Checks if previous value was 0
        // and then updates it
        boolean res
            = val.weakCompareAndSet(10, 6);

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

**Output:** 

```
Previous value: 0
The value was not updated
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # weakCompareAndSet–T4】