# Java 中 long 累加器 get()方法，示例

> 原文:[https://www . geesforgeks . org/long 累加器-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-get-method-in-java-with-examples/)

**java。long 累加器. get()** 是 java 中的一个内置方法，返回 long 累加器对象的当前值。

**语法:**

```
public long get()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回 long 累加器对象的当前值。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the get() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);
        num.accumulate(10);

        // Gets current value
        long x = num.get();

        // Print after get operation
        System.out.println(" the current value is: " + x);
    }
}
```

**输出:**

```
the current value is: 12

```

**程序二** :

```
// Program to demonstrate the get() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(22);
        num.accumulate(10);

        // Gets current value
        long x = num.get();

        // Print after get operation
        System.out.println(" the current value is: " + x);
    }
}
```

**输出:**

```
the current value is: 32

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # get–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#get--)