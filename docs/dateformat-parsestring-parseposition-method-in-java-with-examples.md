# Java 中的日期格式解析(字符串，解析位置)方法，示例

> 原文:[https://www . geesforgeks . org/dateform-parse string-parse position-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformat-parsestring-parseposition-method-in-java-with-examples/)

**解析(字符串** ***the_text*** **、parse position*****position*****)**Date format 类的方法用于从字符串中解析文本以产生日期。方法从起始位置给定的索引处开始分析文本。
**语法:**

```java
public abstract Date parse(String *the_text*, ParsePosition *position*)
```

**参数:**该方法取两个参数:

*   **the_text** :这是*字符串*类型，指的是要解析以产生日期的字符串。
*   **位置**:这是*解析位置*对象类型，是指解析的起始索引信息。

**返回值:**该方法返回从字符串解析的日期，或者在出现错误时返回空值。
下面的程序说明了解析()方法的工作日期格式:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Code to illustrate parse() method

import java.text.*;
import java.util.Calendar;

public class DateFormat_Demo {
    public static void main(String[] args)
    {
        DateFormat DFormat
            = new SimpleDateFormat("MM/ dd/ yy");

        try {
            Calendar cal = Calendar.getInstance();

            // Use of parse() method to parse
            // Date From String
            String dt = "10/ 27/ 16";
            System.out.println("The unparsed"
                               + " string is: " + dt);

            cal.setTime(DFormat.parse(dt));
            System.out.println("Time parsed: "
                               + cal.getTime());
        }
        catch (ParseException except) {
            except.printStackTrace();
        }
    }
}
```

**Output:** 

```java
The unparsed string is: 10/ 27/ 16
Time parsed: Thu Oct 27 00:00:00 UTC 2016
```