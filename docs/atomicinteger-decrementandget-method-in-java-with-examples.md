# Java 中的 AtomicInteger 减量 Get()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-reducandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-decrementandget-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . reductandget()**是 Java 中的一个内置方法，它将以前的值减少一，并在更新后返回数据类型为 **int** 的值。

**语法:**

```
public final int decrementAndGet()
```

**参数:**函数不接受单个参数。
**返回值:**该函数将执行减量操作后的值返回到前一个值。

下面的程序演示了该功能:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrates
// the decrementAndGet() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        System.out.println("Previous value: "
                           + val);

        // Decrement and get
        int res
            = val.decrementAndGet();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**Output:** 

```
Previous value: 0
Current value: -1
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrates
// the decrementAndGet() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        System.out.println("Previous value: "
                           + val);

        // Decrement and get new value
        int res = val.decrementAndGet();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**Output:** 

```
Previous value: 18
Current value: 17
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html #减量获取–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#decrementAndGet--)