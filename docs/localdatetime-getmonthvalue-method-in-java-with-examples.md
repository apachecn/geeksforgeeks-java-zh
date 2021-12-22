# Java 中的 LocalDateTime getMonthValue()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-getmonthvvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-getmonthvalue-method-in-java-with-examples/)

**LocalDateTime 类**的**getmonthvvalue()**方法用于返回年月字段。此方法将 LocalDateTime 中的月份作为 1 到 12 之间的整数返回。

**语法:**

```
public int getMonthValue()

```

**参数:**此方法不接受任何参数。

**返回:**该方法返回**整数值**，该整数值为年月字段，取值范围为 1-12。

下面的程序说明了 LocalDateTime.getMonthValue()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalDateTime.getMonthValue() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-10-23T22:29:10");

        // get Month value field
        int monthvalue = local.getMonthValue();

        // print result
        System.out.println("Month Value: "
                           + monthvalue);
    }
}
```

**输出:**

```
Month Value: 10

```

**程序二:**

```
// Java program to demonstrate
// LocalDateTime.getMonthValue() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2018-12-13T12:28:13");

        // get Month value field
        int monthvalue = local.getMonthValue();

        // print result
        System.out.println("Month Value: "
                           + monthvalue);
    }
}
```

**输出:**

```
Month Value: 12

```

reference:t0]https://docs . Oracle . com/javae/10/docs/API/Java/time/localdatetime . html # getmonthvalue()