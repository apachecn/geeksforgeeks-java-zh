# Java 中的 MonthDay now()方法，示例

> 原文:[https://www . geesforgeks . org/monthday-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-now-method-in-java-with-examples/)

Java 中 **MonthDay** 类的 **now()** 方法用于从默认时区的系统时钟中获取当前的月-日。

**语法:**

```java
public static MonthDay now()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法使用系统时钟和默认时区返回当前**月-日**。

下面的程序说明了 Java 中 MonthDay 的 now()方法:

**程序 1:**

```java
// Java program to demonstrate
// MonthDay.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of MonthDay class
        MonthDay result = MonthDay.now();

        // print both month and day
        System.out.println("MonthDay: "
                           + result);
    }
}
```

**输出:**

```java
MonthDay: --05-09

```

**程序二:**

```java
// Java program to demonstrate
// MonthDay.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of MonthDay class
        MonthDay result = MonthDay.now();

        // print only month
        System.out.println("Month: "
                           + result.getMonth());
    }
}
```

**输出:**

```java
Month: MAY

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#now())