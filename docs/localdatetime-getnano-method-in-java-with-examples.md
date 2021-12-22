# Java 中的 LocalDateTime getNano()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getnano-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getnano-method-in-java-with-examples/)

一个**本地日期时间类**的 **getNano()** 方法用于返回纳米秒的字段。此方法返回一个介于 0 到 999，999，999 之间的整数值，代表纳米秒的值。

**语法:**

```
public int getNano()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回一个**整数值**，它是一个介于 0 到 999，999，999 之间的整数，代表纳米秒的值。

下面的程序说明了 LocalDateTime.getNano()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-13T12:28:13.63");

        // get NanoOfSecond
        int nanoOfSecond = local.getNano();

        // print result
        System.out.println("NanoOfSecond: "
                           + nanoOfSecond);
    }
}
```

**输出:**

```
NanoOfSecond: 630000000

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getNano() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-11-23T02:48:53.93");

        // get NanoOfSecond
        int nanoOfSecond = local.getNano();

        // print result
        System.out.println("NanoOfSecond: "
                           + nanoOfSecond);
    }
}
```

**输出:**

```
NanoOfSecond: 930000000

```

参考:t0[https://docs . Oracle . com/javae/10/docs/API/Java/time/localdatetime . html # getnano()]t1]