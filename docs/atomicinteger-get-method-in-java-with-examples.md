# atomicintiger get()方法在 Java 中的示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-get-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . get()**是 Java 中的一个内置方法，它返回日期类型 int 的当前值。

**语法:**

```
public final int get()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前值

下面的程序演示了该功能:

**程序 1:**

```
// Java Program to demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Gets the current value
        int res = val.get();

        System.out.println("current value: "
                           + res);
    }
}
```

**输出:**

```
Previous value: 7
current value: 7

```

程序二:

```
// Java Program to demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val = new AtomicInteger(18);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: " + val);

        // Gets the current value
        int res = val.get();

        System.out.println("current value: " + res);
    }
}
```

**输出:**

```
Previous value: 25
current value: 25

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # get–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#get--)