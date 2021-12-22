# Java 中 long 累加器 longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/long 累加器-long value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/longaccumulator-longvalue-method-in-java-with-examples/)

**java。long 累加器. longValue()** 是 java 中的一个内置方法，相当于 get()方法，也就是说这个方法只是返回当前值。

**语法:**

```
public long longValue()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回当前值。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the longValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // longValues current value
        num.longValue();

        // Print after longValue operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```
the current value is: 52

```

**程序二** :

```
// Program to demonstrate the longValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(5);
        num.accumulate(10);

        // longValues current value
        num.longValue();

        // Print after longValue operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```
the current value is: 15

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # long value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#longValue--)