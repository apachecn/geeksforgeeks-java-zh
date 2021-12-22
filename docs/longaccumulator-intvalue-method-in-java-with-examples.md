# Java 中 long 累加器 intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/long 累加器-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-intvalue-method-in-java-with-examples/)

**java。long 累加器. intValue()** 是 java 中的一个内置方法，它在缩小基元转换后将当前值作为 int 返回。

**语法:**

```java
public int intValue()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法在收缩基元转换后将当前值作为 int 返回。

下面的程序说明了上述方法:

**程序 1** :

```java
// Program to demonstrate the intValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // Print before intValue operation
        System.out.println(" the old value is: " + num);

        // intValues current value
        num.intValue();

        // Print after intValue operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出:**

```java
the old value is: 52
the current value is: 52

```

**程序二** :

```java
// Program to demonstrate the intValue() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(4);
        num.accumulate(4);

        // Print before intValue operation
        System.out.println(" the old value is: " + num);

        // intValues current value
        num.intValue();

        // Print after intValue operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```java
the old value is: 8
the current value is: 8

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # int value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#intValue--)