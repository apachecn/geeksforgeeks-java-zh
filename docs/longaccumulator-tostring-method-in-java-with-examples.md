# Java 中 long 累加器 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/long 累加器-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longaccumulator-tostring-method-in-java-with-examples/)

**java。long 累加器. toString()** 是 java 中的一个内置方法，它返回 long 累加器实例当前值的字符串表示形式。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回当前值的字符串表示形式。

下面的程序说明了上述方法:

**程序 1** :

```java
// Program to demonstrate the toString() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        num.get();
        // before toString the value is
        System.out.println(" the old value is: " + num);
        ;

        // toStrings current value
        num.toString();

        // Print after toString operation
        System.out.println(" the current value is: " + num);
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
// program to demonstrate the toString() method

import java.lang.*;
import java.util.concurrent.atomic.LongAccumulator;

public class GFG {
    public static void main(String args[])
    {
        LongAccumulator num = new LongAccumulator(Long::sum, 0L);

        // accumulate operation on num
        num.accumulate(5);
        num.accumulate(10);

        num.get();
        // before toString the value is
        System.out.println(" the old value is: " + num);

        // toStrings current value
        num.toString();

        // Print after toString operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```java
the old value is: 15
 the current value is: 15

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/long 累加器. html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/LongAccumulator.html#toString--)