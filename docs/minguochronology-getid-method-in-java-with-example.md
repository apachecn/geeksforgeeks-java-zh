# Java 中的 Minguo 年表 getId()方法，示例

> 原文:[https://www . geeksforgeeks . org/minguoberogram-getid-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-getid-method-in-java-with-example/)

类的 **getId()** 方法用于检索 getId()方法被撤销的特定年表的标识状态。

**语法:**

```
public String getId()
```

**参数:**此方法不接受任何参数作为参数。

**返回值:**该方法返回 getId()方法被撤销的特定年表的标识状态。

以下是说明 **getId()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// getId() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now();

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using getId() method
        String id = crono.getId();

        // display the result
        System.out.println("id : " + id);
    }
}
```

**输出:**

```
id : Minguo

```

**例 2:**

```
// Java program to demonstrate
// getId() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // MinguoDate Object
        MinguoDate hidate
            = MinguoDate.now(Clock.systemDefaultZone());

        // getting MinguoChronology
        // used in MinguoDate
        MinguoChronology crono
            = hidate.getChronology();

        // getting id of this Chronology
        // by using getId() method
        String id = crono.getId();

        // display the result
        System.out.println("id : " + id);
    }
}
```

**输出:**

```
id : Minguo

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html # Getid–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#getId--)