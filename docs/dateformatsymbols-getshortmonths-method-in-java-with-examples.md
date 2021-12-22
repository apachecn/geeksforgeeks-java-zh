# Java 中的日期格式符号 getShortMonths()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-getshortmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-getshortmonths-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getShortMonths()** 方法用于获取字符串格式的日历月份的简称。

**语法:**

```java
public String[] getMonths()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以字符串格式返回月份的**简称**。

下面的程序说明了 getShortMonths()方法的使用。
**例 1:**

```java
// Java code to demonstrate getShortMonths()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {

        int i;

        // Initializing DateFormatSymbols
        String months[]
            = new DateFormatSymbols()
                  .getShortMonths();

        for (i = 0; i < months.length - 1; i++) {

            // Displaying the short months
            System.out.println(
                "Month = " + months[i]);
        }
    }
}
```

**Output:**

```java
Month = Jan
Month = Feb
Month = Mar
Month = Apr
Month = May
Month = Jun
Month = Jul
Month = Aug
Month = Sep
Month = Oct
Month = Nov
Month = Dec

```

**例 2:**

```java
// Java code to demonstrate getShortMonths()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {

        int i;

        // Initializing DateFormatSymbols
        String months[]
            = new DateFormatSymbols()
                  .getShortMonths();

        for (i = 0; i < months.length / 2; i++) {

            // Displaying the short months
            System.out.println(
                "Month " + i + " = " + months[i]);
        }
    }
}
```

**Output:**

```java
Month 0 = Jan
Month 1 = Feb
Month 2 = Mar
Month 3 = Apr
Month 4 = May
Month 5 = Jun

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getShortMonths–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getShortMonths--)