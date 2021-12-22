# Java 中的持续时间解析(CharSequence)方法，示例

> 原文:[https://www . geesforgeks . org/duration-parser charsequence-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-parsecharsequence-method-in-java-with-examples/)

**java.time 包**中 **Duration 类**的**解析(CharSequence)** 方法用于从作为参数传递的字符串中获取 Duration。要解析的字符串的格式为“PnDTnHnMn.nS”，其中“nDT”表示“n”天，“nH”表示“n”小时数，“nM”表示“n”分钟数，“nS”表示“n”秒钟数。接受的格式基于国际标准化组织 8601 持续时间格式。

**语法:**

```java
public static Duration parse(CharSequence text)

```

**参数:**该方法接受一个参数**文本**，它是要解析为持续时间的字符序列。

**返回值:**该方法返回一个**持续时间**，以字符序列的形式表示经过的时间作为参数。

**异常:**如果文本无法解析为持续时间，此方法将引发**datetime arseeexception**。

以下示例说明了 Duration.parse()方法:

**例 1:**

```java
// Java code to illustrate parse() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "P2DT3H4M";

        // Duration using parse() method
        Duration duration
            = Duration.parse(time);

        System.out.println(duration.getSeconds());
    }
}
```

**输出:**

```java
183840

```

**示例 2:** 演示日期时间例外

```java
// Java code to illustrate parse() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Get the text
        String time = "M";

        try {
            // Duration using parse() method
            Duration duration
                = Duration.parse(time);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception:
 java.time.format.DateTimeParseException:
 Text cannot be parsed to a Duration

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # parse-Java . lang . charsequence-](https://docs.oracle.com/javase/9/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)