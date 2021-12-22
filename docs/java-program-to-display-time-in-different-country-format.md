# Java 程序以不同国家格式显示时间

> 原文:[https://www . geesforgeks . org/Java-程序到显示-不同国家时间-格式/](https://www.geeksforgeeks.org/java-program-to-display-time-in-different-country-format/)

[地区类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)和[日期格式类](https://www.geeksforgeeks.org/dateformat-format-method-in-java-with-examples/)用于显示时间不同的国家格式。

Java 中的 DateFormat 类用于格式化日期。指定的日期可以格式化为数据/时间字符串。例如，日期可以格式化为:mm/dd/yyyy。日期格式类不同步。语言环境对象在逻辑上由语言、脚本、国家、变体、扩展名等字段组成。

Java Locale 类对象表示特定的地理、文化或政治区域。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Display Time in Different Country Format

import java.text.DateFormat;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception
    {
        Date d1 = new Date();

        // creating a new locale for England Format
        Locale locEngland = new Locale("en", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat de = DateFormat.getDateInstance(
                        DateFormat.FULL, locEngland);

        System.out.println("England Format: "
                           + de.format(d1));

        // creating a new locale for Italian Format
        Locale locItalian = new Locale("it", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat di = DateFormat.getDateInstance(
                        DateFormat.FULL, locItalian);

        System.out.println("Italian Format: "
                           + di.format(d1));

        // creating a new locale for Russian Format
        Locale locRussian = new Locale("ru", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat dr = DateFormat.getDateInstance(
                        DateFormat.FULL, locRussian);

        System.out.println("Russian Format: "
                           + dr.format(d1));

        // creating a new locale for French Format
        Locale locFrench = new Locale("fr", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat df = DateFormat.getDateInstance(
                        DateFormat.FULL, locFrench);

        System.out.println("French Format: "
                           + df.format(d1));

        // creating a new locale for Spanish Format
        Locale locSpanish = new Locale("es", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat ds = DateFormat.getDateInstance(
                        DateFormat.FULL, locSpanish);

        System.out.println("Spanish Format: "
                           + ds.format(d1));

        // creating a new locale for chinese Format
        Locale locChinese = new Locale("cn", "ch");

        // initializing the date formatter and converting
        // the date
        DateFormat dc = DateFormat.getDateInstance(
                        DateFormat.FULL, locChinese);

        System.out.println("Chinese Format: "
                           + dc.format(d1));
    }
}
```

**Output**

```java
England Format: Tuesday, 5 January 2021
Italian Format: marted?, 5 gennaio 2021
Russian Format: ???????, 5 ?????? 2021 ?.
French Format: mardi, 5 janvier 2021
Spanish Format: martes, 5 de enero de 2021
Chinese Format: 2021 Jan 5, Tue

```