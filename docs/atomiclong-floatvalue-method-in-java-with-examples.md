# Java 中的 AtomicLong floatValue()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-floatvalue-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLong . Float value()**是 Java 中的一个内置方法，它在执行原语转换后，将 atomic clong 的当前值作为 **Float** 数据类型返回。

**语法:**

```
public float floatValue()
```

**参数:**函数不接受任何参数。

**返回值:**该函数返回转换为类型 float 后该对象表示的数值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the floatValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Gets the float value
        float res = val.floatValue();

        System.out.println("float value: "
                           + res);
    }
}
```

**输出:**

```
Previous value: 7
float value: 7.0

```

**程序二:**

```
// Java program that demonstrates
// the floatValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        val.addAndGet(7);

        // Gets the float value
        System.out.println("Previous value: "
                           + val);

        // Decreases the value by 1
        float res = val.floatValue();

        System.out.println("float value: "
                           + res);
    }
}
```

**输出:**

```
Previous value: 25
float value: 25.0

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # float value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#floatValue--)