# Java 中的 hijrah 年表 dateNow(ZoneId)方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrah 年表-datenowzoneid-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahchronology-datenowzoneid-method-in-java-with-example/)

**Java . time . chrono . Hijrah 年表**类的 **dateNow()** 方法用于从指定时区的系统时钟中获取根据 Hijrah 日历系统的当前本地日期。

**语法:**

```java
public HijrahDate dateNow(ZoneId zone)
```

**参数**:该方法以 id 区的**对象为参数。**

**返回值:**该方法根据 Hijrah 日历系统从指定的时钟对象返回本地日期。

以下是举例说明 **dateNow()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.systemDefault();

            // getting HijrahDate for the
            // given zoneid object
            // by using dateNow() method
            HijrahDate date = crono.dateNow(id);

            // display the result
            System.out.println("HijrahDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
HijrahDate is: Hijrah-umalqura AH 1441-05-27

```

**例 2:**

```java
// Java program to demonstrate
// dateNow() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing  HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // getting HijrahChronology used in HijrahDate
            HijrahChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.of("Europe/Paris");
            ;

            // getting HijrahDate for the
            // given zoneid object
            // by using dateNow() method
            HijrahDate date = crono.dateNow(id);

            // display the result
            System.out.println("HijrahDate is: "
                               + date);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
HijrahDate is: Hijrah-umalqura AH 1441-05-27

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/HijRahEr 年表. html # dateNow-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahChronology.html#dateNow-java.time.ZoneId-)