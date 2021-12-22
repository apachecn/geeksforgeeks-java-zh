# Java 中的 LocalTime getNano()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-getnano-method-in-java-with-examples/)

一个**本地时间类**的 **getNano()** 方法用于返回纳米秒的场。此方法返回一个介于 0 到 999，999，999 之间的整数值，即一秒的纳米数。

**语法:**

```
public int getNano()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个**整数值**，代表毫微秒，范围从 0 到 999，999，999。

下面的程序说明了 getNano()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // get Nano field using getNano()
        int Nano = time.getNano();

        // print result
        System.out.println("Nano Field: "
                           + Nano);
    }
}
```

**输出:**

```
Nano Field: 630000000

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("23:14:30.53");

        // get Nano field using getNano()
        int Nano = time.getNano();

        // print result
        System.out.println("Nano Field: "
                           + Nano);
    }
}
```

**输出:**

```
Nano Field: 530000000

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # getNano()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#getNano())