# Java 中的 LogRecord setInstant()方法，带示例

> 原文:[https://www . geesforgeks . org/log record-set instant-method-in-Java-with-examples/](https://www.geeksforgeeks.org/logrecord-setinstant-method-in-java-with-examples/)

**Java . lang . reflect . log record**的 **setInstant()** 方法用于设置事件发生的这个瞬间，这有助于记录事件的瞬间。如果给定的瞬间表示时间线上的某个点在未来或过去太远，无法适应长毫秒和纳秒调整，将引发算术异常。

**语法:**

```java
public void setInstant(Instant instant)

```

**参数:**此方法接受**瞬间**，即事件发生的瞬间。

**返回**:此方法返回**无**。

**异常:**这个方法会抛出以下异常:

*   **NullPointRexception**–如果 instant 为空。
*   **算术异常**–如果在调用 instant.toEpochMilli()时会出现数字溢出。

下面的程序说明了 setInstant()方法:
**程序 1:**

```java
// Java program to illustrate
// setInstant() method

import java.time.Instant;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {
        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "Hi Logger");

        // set Instant time
        logRecord.setInstant(instant);
        System.out.println(
            "Event Time "
            + logRecord.getInstant()
                  .toString());
    }
}
```

**Output:**

```java
Event Time 2018-12-30T19:34:50.630Z

```

**程序 2:**

```java
// Java program to illustrate
// setInstant() method

import java.time.Instant;
import java.util.logging.Level;
import java.util.logging.LogRecord;

public class GFG {

    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.now();

        // Create LogRecord object
        LogRecord logRecord = new LogRecord(
            Level.parse("800"),
            "GFG Logger");

        // set Instant time
        logRecord.setInstant(instant);

        System.out.println0(
            "Event Time "
            + logRecord.getInstant()
                  .toString());
    }
}
```

**Output:**

```java
Event Time 2019-10-20T19:32:50.818428ZEvent Time 09 Sep 2001 07:16:39:900 +0530

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/logging/logrecord . html # setInstant(Java . time . instant)](https://docs.oracle.com/javase/10/docs/api/java/util/logging/LogRecord.html#setInstant(java.time.Instant))