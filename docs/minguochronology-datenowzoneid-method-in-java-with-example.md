# Java 中的 Minguo 年表 dateNow(ZoneId)方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo 年表-datenowzoneid-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-datenowzoneid-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **dateNow()** 方法用于从指定时区的系统时钟中获取根据 Minguo 日历系统的当前本地日期。

**语法:**

```
public MinguoDate dateNow(ZoneId zone)
```

**参数**:该方法以 id 区的**对象为参数。**

**返回值:**该方法从指定的时钟对象返回根据民国日历系统的本地日期。

以下是举例说明 **dateNow()** 方法的例子:

**例 1:**

```
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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.systemDefault();

            // getting MinguoDate for the
            // given zoneid object
            // by using dateNow() method
            MinguoDate date = crono.dateNow(id);

            // display the result
            System.out.println("MinguoDate is: "
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

```
MinguoDate is: Minguo ROC 109-04-15

```

**例 2:**

```
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
            // creating and initializing MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting MinguoChronology used in MinguoDate
            MinguoChronology crono = hidate.getChronology();

            // creating and initializing ZoneId object
            ZoneId id = ZoneId.of("Europe/Paris");

            // getting MinguoDate for the
            // given zoneid object
            // by using dateNow() method
            MinguoDate date = crono.dateNow(id);

            // display the result
            System.out.println("MinguoDate is: "
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

```
MinguoDate is: Minguo ROC 109-04-15

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html # dateNow-Java . time . zoneid-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#dateNow-java.time.ZoneId-)