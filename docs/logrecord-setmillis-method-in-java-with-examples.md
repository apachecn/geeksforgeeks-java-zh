# Java 中的 LogRecord setMillis()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-setmillis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setmillis-method-in-java-with-examples/)

**Java . util . LogRecord**的 **setMillis()** 方法用于在 log record 中设置事件时间。自 1970 年以来，此事件时间以毫秒为单位。

**语法:**

```java
public void setMillis(long millis)

```

**参数:**该方法接受**毫秒**作为参数，该参数是 1970 年以来以毫秒为单位的事件时间

**返回**:此方法不返回任何内容。

下面的程序说明了 setMillis()方法:
**程序 1:**

```java
// Java program to illustrate setMillis() method

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

        // set event time
        logRecord.setMillis(999999999900L);

        // get event time and convert it into date
        DateFormat simple
            = new SimpleDateFormat(
                "dd MMM yyyy HH:mm:ss:SSS Z");

        Date result
            = new Date(logRecord.getMillis());

        System.out.println("Event Time "
                           + simple.format(result));
    }
}
```

**Output:**

```java
Event Time 09 Sep 2001 01:46:39:900 +0000

```

**程序 2:**

```java
// Java program to illustrate setMillis() method

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
            "GFG Logger");

        // set event time
        logRecord.setMillis(9632736138L);

        // get event time and convert it into date
        DateFormat simple
            = new SimpleDateFormat(
                "dd MMM yyyy");

        Date result
            = new Date(logRecord.getMillis());

        System.out.println("Event Date: "
                           + simple.format(result));
    }
}
```

**Output:**

```java
Event Date: 22 Apr 1970

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/logging/logrecord . html # setMillis-long-](https://docs.oracle.com/javase/8/docs/api/java/util/logging/LogRecord.html#setMillis-long-)