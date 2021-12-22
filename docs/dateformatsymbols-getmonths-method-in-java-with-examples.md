# Java 中的日期格式符号 getMonths()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-getmonths-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-getmonths-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的 **getMonths()** 方法用于获取字符串格式的日历月份名称。

**语法:**

```java
public String[] getMonths()
```

**参数:**该方法不取任何参数。

**返回值:**该方法以字符串格式返回月份的名称。

下面的程序说明了 getMonths()方法的使用。

**例 1:**

```java
// Java code to demonstrate getMonths()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {
        int i;

        // Initializing DateFormatSymbols
        String months[]
            = new DateFormatSymbols().getMonths();

        for (i = 0; i < months.length - 1; i++) {

            // Displaying the months
            System.out.println("Month = "
                               + months[i]);
        }
    }
}
```

**输出:**

```java
Month = January
Month = February
Month = March
Month = April
Month = May
Month = June
Month = July
Month = August
Month = September
Month = October
Month = November
Month = December

```

**例 2:**

```java
// Java code to demonstrate getMonths()

import java.text.DateFormatSymbols;

public class DateFormat_Main {
    public static void main(String args[])
    {

        int i;

        // Initializing DateFormatSymbols
        String months[]
            = new DateFormatSymbols().getMonths();

        for (i = 0; i < months.length / 2; i++) {

            // Displaying the months
            System.out.println("Month " + i
                               + " = " + months[i]);
        }
    }
}
```

**输出:**

```java
Month 0 = January
Month 1 = February
Month 2 = March
Month 3 = April
Month 4 = May
Month 5 = June

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # getMonths–](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#getMonths--)