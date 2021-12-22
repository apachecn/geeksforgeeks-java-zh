# Java 中 long 累加器 doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/long 累加器-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/longaccumulator-doublevalue-method-in-java-with-examples/)

**java。long 累加器. doubleValue()** 是 java 中的一个内置方法，在扩展原语转换后以双精度形式返回当前值。

**语法:**

```
public double doubleValue()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法在加宽图元转换后以双精度形式返回当前值。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // Print before doubleValue operation
        System.out.println(" the old value is: " + num);

        // doubleValues current value
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出:**

```
the old value is: 52
the current value is: 52

```

**程序二** :

```
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(4);
        num.accumulate(10);

        // Print before doubleValue operation
        System.out.println(" the old value is: " + num);

        // doubleValues current value
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出:**

```
the old value is: 14
the current value is: 14

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # double value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#doubleValue--)