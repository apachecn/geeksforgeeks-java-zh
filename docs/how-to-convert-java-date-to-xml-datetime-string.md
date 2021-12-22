# 如何将 Java Date 转换为 XML DateTime 字符串？

> 原文:[https://www . geesforgeks . org/how-convert-Java-date-to-XML-datetime-string/](https://www.geeksforgeeks.org/how-to-convert-java-date-to-xml-datetime-string/)

为了定义日期和时间，使用了**日期时间**数据类型。日期时间的定义格式为“**YYYY-MM-DDTHH:MM:ss”**，其中:

*   **YYYY** 表示年份
*   **MM** 代表月份
*   **DD** 显示当天
*   **T** 表示所需时间段的开始。
*   **Hh** 决定小时
*   **毫米**代表分钟
*   **ss** 表示秒

**例:** 2002-05-30T09:00:00

**什么是 XML DateTime 格式的时区？**

为了指定时区，我们可以通过在时间后面插入“Z”来输入 UTC 时间中的日期时间，

**示例:**

```java
2002-05-30T09:30:10Z  
```

或者，我们可以通过在时间后添加正时间或负时间来确定与世界协调时时间的偏差，

**示例:**

```java
2002-05-30T09:30:10-06:00
2002-05-30T09:30:10+06:00
```

因此，时区可以定义为“Z”(世界协调时)或“(+|-)hh:mm”。未定义的时区称为“未确定”文字“Z”(祖鲁语)用作时区指示器，表示在时间结束时添加的时间是世界协调时。

**什么是时间偏移？**

时间偏移是从协调世界时(UTC)时间中添加或减去的时间量，以获得特定地点的当前时间。

**将 Java 日期转换为 XML 日期时间字符串的方法:**

*   首先我们创建一个简单日期格式的对象。这个类解析并格式化 Java 中的日期和时间。
*   然后，我们创建一个[字符串缓冲区](https://www.geeksforgeeks.org/stringbuffer-class-in-java/)，它将保存 XML 格式的字符串。
*   此外，我们还计算了区域偏移量。它确定从格林威治/世界协调时时间偏移的时区。时区偏移量是时区与格林威治时间/世界协调时之间的时间差。这通常是固定的小时和分钟数。世界不同的地方有不同的时区偏移。例如，印度比格林威治时间/世界协调时早 05:30。
*   最后，我们将所有需要的信息组合在一个字符串中，这个字符串就是格式化的 XML 字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Convert Java Date to XML DateTime String

import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;

public class GFG {

    public static void main(String[] args)
    {

        // formatting time
        SimpleDateFormat format1 = new SimpleDateFormat("yyyy-MM-dd");
        SimpleDateFormat format2 = new SimpleDateFormat("HH:mm:ss");

        // create a StringBuffer(in order to use its append
        // functionality) to store the date in XML DateTime
        // format
        StringBuffer buff = new StringBuffer();

        // get the date of the system by creating an
        // instance of the Date class
        Date date = new Date();

        // append the formated date(yyyy-MM-dd) in the
        // buffer
        buff.append(format1.format(date));

        // append T
        buff.append('T');

        // and finally append the formated time(HH:mm:ss) in
        // buffer
        buff.append(format2.format(date));

        // calculating time zone
        // get the calendar instance in order to get the
        // time offset
        Calendar calendar = Calendar.getInstance();

        // The get(int field_value) method of Calendar class
        // is used to return the value of the given calendar
        // field in the parameter.
        int offset = calendar.get(calendar.ZONE_OFFSET)
                     / (1000 * 60);

        // add the sign(+/-) according to the value of the
        // offset
        if (offset < 0) {
            buff.append('-');

            // if the offset is negative make it positive by
            // multiplying it with -1, we will be using it
            //further
            offset *= -1;
        }
        else {
            buff.append('+');
        }

        // get the hour from the offset and store it in a
        // String
        String s1 = String.valueOf(offset / 60);

        // check if the retrieved hour is single digit or
        // two digit in case of single digit, add 0 before
        // the significant value
        for (int i = s1.length(); i < 2; i++) {
            buff.append('0');
        }

        // then finally append the s1 in our buffer
        buff.append(s1);
        buff.append(':');

        // now retrieve the minutes from offset, and
        // validate it in the same way as we did for the hour
        String s2 = String.valueOf(offset % 60);

        for (int i = s2.length(); i < 2; i++) {
            buff.append('0');
        }

        // append the minutes in buffer
        buff.append(s2);

        // finally we are done formatting the Java Date time
        // into XML DateTime format convert the buffer into
        // the String, and print it
        System.out.println(buff.toString());
    }
}
```

**Output**

```java
2021-02-23T10:38:30+00:00
```