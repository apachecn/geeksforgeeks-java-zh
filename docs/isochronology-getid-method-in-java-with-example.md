# Java 中的等时 getId()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-getid-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-getid-method-in-java-with-example/)

**Java . time . chrono . isochronology 类**的 **getId()** 方法用于检索 getId()方法被撤销的特定年表的标识状态。

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
        // LocalDate Object
        LocalDate hidate = LocalDate.now();

        // getting IsoChronology
        // used in LocalDate
        IsoChronology crono
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
id : ISO

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
        // LocalDate Object
        LocalDate hidate = LocalDate.now(Clock.systemDefaultZone());

        // getting IsoChronology
        // used in LocalDate
        IsoChronology crono
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
id : ISO

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # Getid–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#getId--)