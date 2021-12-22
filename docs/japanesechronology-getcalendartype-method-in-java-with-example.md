# Java 中的日本年表 getCalendarType()方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-getcalendartype-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesechronology-getcalendartype-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **getCalendarType()** 方法用于检索这个日语年表系统下的日历类型。
**语法:**

```
public String getCalendarType()
```

**参数:**此方法不接受任何参数作为参数。
**返回值:**这个方法返回的**类型的日历**就在这个日本的时间系统下。
以下是举例说明 **getCalendarType()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // JapaneseDate Object
        JapaneseDate hidate
            = JapaneseDate.now();

        // getting JapaneseChronology
        // used in JapaneseDate
        JapaneseChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```
Type of Calendar : japanese

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// getCalendarType() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // JapaneseDate Object
        JapaneseDate hidate
            = JapaneseDate.now(
                Clock.systemDefaultZone());

        // getting JapaneseChronology
        // used in JapaneseDate
        JapaneseChronology crono
            = hidate.getChronology();

        // getting type of Calendar
        // by using getCalendarType() method
        String era = crono.getCalendarType();

        // display the result
        System.out.println("Type of Calendar : "
                           + era);
    }
}
```

**Output**

```
Type of Calendar : japanese

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese yestereo . html # getCalendarType–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#getCalendarType--)