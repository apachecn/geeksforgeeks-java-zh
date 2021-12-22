# 日期格式符号设置工作日()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-set weekdays-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-setweekdays-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的**setWeekdays(String[]*****【new weekds】*****)**方法用于将字符串格式的日历的工作日名称设置为一些不同的字符串。例如，“星期日”可以改为“星期五”，“星期一”可以改为“星期三”或其他随机字符串。

**语法:**

```java
public void setWeekdays(String[] *newWeekds*)
```

**参数:**该方法取一个参数 ***newWeekds*** ，该参数是 [*字符串*](https://www.geeksforgeeks.org/strings-in-java/) 类型的数组，指的是在现有工作日中要替换的新字符串。
**返回值:**该方法以字符串形式返回工作日的**修改名称。
下面的程序说明了 setWeekdays()方法的使用。
**例 1:****

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate setWeekdays()

import java.text.DateFormatSymbols;
import java.util.Locale;

public class DateFormat_Main {
    public static void main(String args[])
    {

        // Initialising DateFormatSymbols object
        DateFormatSymbols format
            = new DateFormatSymbols(
                new Locale("en", "US"));

        // Taking the default short weekdays
        String[] Days = format.getWeekdays();

        // Displaying the original
        System.out.print("Original: ");
        for (int i = 1; i < Days.length; i++) {
            System.out.print(Days[i] + "  ");
        }
        System.out.println();

        // Taking an alternative names with
        // additional random strings
        String[] modDays = { "WEDNESDAY", "THURSDAY",
                             "FRIDAY", "MONDAY",
                             "TUESDAY", "SUNDAY",
                             "SATURDAY" };

        // Setting the default into modified
        format.setWeekdays(modDays);

        // Displaying the modified string
        String[] modifiedDays = format.getWeekdays();

        System.out.print("Modified: ");
        for (int i = 0; i < modifiedDays.length; i++) {
            System.out.print(modifiedDays[i] + "  ");
        }
    }
}
```

**Output:** 

```java
Original: Sunday  Monday  Tuesday  Wednesday  Thursday  Friday  Saturday  
Modified: WEDNESDAY  THURSDAY  FRIDAY  MONDAY  TUESDAY  SUNDAY  SATURDAY
```