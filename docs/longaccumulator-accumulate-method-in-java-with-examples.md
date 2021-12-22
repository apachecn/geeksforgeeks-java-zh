# Java 中 long 累加器累加()方法，示例

> 原文:[https://www . geesforgeks . org/long 累加器-grade-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-accumulate-method-in-java-with-examples/)

**java。long 累加器. aggregate()**是 java 中的一个内置方法，用给定的值更新特定的 long 累加器对象。

**语法:**

```
public void accumulate(long x)

```

**参数:**该方法接受单个参数 **x** ，即当前 long 累加器对象更新的值。

**返回值:**该方法返回更新后的值。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the accumulate() method
import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);

        // Print after accumulate
        System.out.println("After update the value is: " + num);
    }
}
```

**输出:**

```
After update the value is: 2

```

**程序二** :

```
// Program to demonstrate the accumulate() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(5);

        // Print after accumulate
        System.out.println("After update the value is: " + num);
    }
}
```

**输出:**

```
After update the value is: 5

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # aggregate-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#accumulate-long-)