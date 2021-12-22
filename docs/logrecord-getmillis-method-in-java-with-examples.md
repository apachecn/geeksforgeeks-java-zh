# Java 中的 LogRecord getMillis()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-getmillis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-getmillis-method-in-java-with-examples/)

**Java . lang . reflect . LogRecord**的 **getMillis()** 方法用于获取 log record 中的事件时间。自 1970 年以来，此事件时间以毫秒为单位。

**语法:**

```
public long getMillis()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回 1970 年以来**截断的事件时间**，单位为毫秒。

下面的程序说明了 getMillis()方法:
**程序 1:**

```
// Java program to illustrate
// getMillis() method

import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");
        logRecord.setMillis(999999999900L);

        // get event time
        long millis = logRecord.getMillis();

        // get event time and
        // convert it into a date
        DateFormat simple
            = new SimpleDateFormat(
                "dd MMM yyyy HH:mm:ss:SSS Z");

        Date result
            = new Date(millis);

        System.out.println(
            "Event Time "
            + simple.format(result));
    }
}
```

**Output:**

```
Event Time 09 Sep 2001 07:16:39:900 +0530

```

**程序 2:**

```
// Java program to illustrate
// getMillis() method

import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("600"),
            "GFG Logger");
        logRecord.setMillis(9632736138L);

        // get event time
        long millis = logRecord.getMillis();

        // get event time and
        // convert it into a date
        DateFormat simple
            = new SimpleDateFormat(
                "dd MMM yyyy HH:mm:ss:SSS Z");

        Date result
            = new Date(millis);

        System.out.println(
            "Event Time "
            + simple.format(result));
    }
}
```

**Output:**

```
Event Time 22 Apr 1970 17:15:36:138 +0530

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # getMillis()](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#getMillis())