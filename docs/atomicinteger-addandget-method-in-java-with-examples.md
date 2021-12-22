# Java 中的 AtomicInteger addAndGet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicinteger-addandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-addandget-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . addandget()**是 Java 中的一个内置方法，它将函数参数中传递的值与之前的值相加，并返回数据类型为 **int** 的新的更新值。

**语法:**

```
public final int addAndGet(int val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要添加的值。

**返回值:**函数在加法完成后返回整数值。

下面的程序演示了该功能:

**程序 1:**

```
// Java Program to demonstrates
// the addandget() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger();

        // Update the value
        int c = val.addAndGet(6);

        // Prints the updated value
        System.out.println("Updated value: "
                           + c);
    }
}
```

**输出:**

```
Updated value: 6

```

**程序二:**

```
// Java Program to demonstrates
// the addandget() function

import java.util.concurrent.atomic.AtomicInteger;
public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // adds the value to 18
        val.addAndGet(6);

        // Prints the updated value
        System.out.println("Updated value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: 18
Updated value: 24

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicinteger . html # addAndGet-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#addAndGet-int-)