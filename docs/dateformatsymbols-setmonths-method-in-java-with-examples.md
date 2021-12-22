# Java 中的日期格式符号设置月份()方法，带示例

> 原文:[https://www . geesforgeks . org/date format symbols-set months-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-setmonths-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的**设置月份(字符串[] *newMonth* )** 方法是将字符串格式的日历月份名称设置成一些不同的字符串。例如，“一月”可以改为“二月”，“六月”可以改为“极客”等。

**语法:**

```java
public void setMonths(String[] *newMonth*)
```

**参数:**该方法取一个参数 ***【新月】*** ，它是 *[字符串](https://www.geeksforgeeks.org/strings-in-java/)* 类型的数组，指的是在现有月份中要替换的新字符串。

**返回值:**该方法以字符串格式返回月份的修改名称。

下面的程序说明了 setMonths()方法的使用。
**例 1:**

```java
// Java code to demonstrate setMonths()

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
        String[] Days = format.getMonths();

        // Displaying the original
        System.out.println("Original: ");
        for (int i = 0; i < Days.length; i++) {
            System.out.println(Days[i] + "  ");
        }

        // Taking an alternative names with
        // additional random strings
        String[] modDays = { "GEEK", "FOR",
                             "GEEK", "DECEMBER",
                             "NOVEMBER", "JAN",
                             "FEB" };

        // Setting the default into modified
        format.setMonths(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getMonths();

        System.out.println("Modified: ");
        for (int i = 0; i < modifiedDays.length; i++) {
            System.out.println(modifiedDays[i] + "  ");
        }
    }
}
```

**Output:**

```java
Original: 
January  
February  
March  
April  
May  
June  
July  
August  
September  
October  
November  
December  

Modified: 
GEEK  
FOR  
GEEK  
DECEMBER  
NOVEMBER  
JAN  
FEB

```

**例 2:**

```java
// Java code to demonstrate setMonths()

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
        String[] Days = format.getMonths();

        // Displaying the original
        System.out.println("Original: ");

        for (int i = 0; i < Days.length; i++) {
            System.out.println(Days[i] + "  ");
        }

        // Taking an alternative names with
        // additional random strings
        String[] modDays = { "123", "456",
                             "JAN", "FEB",
                             "NOV", "Dec",
                             "May" };

        // Setting the default into modified
        format.setMonths(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getMonths();

        System.out.println("Modified: ");
        for (int i = 0; i < modifiedDays.length; i++) {
            System.out.println(modifiedDays[i] + "  ");
        }
    }
}
```

**Output:**

```java
Original: 
January  
February  
March  
April  
May  
June  
July  
August  
September  
October  
November  
December  

Modified: 
123  
456  
JAN  
FEB  
NOV  
Dec  
May

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # setMonths-Java . lang . string:A-](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#setMonths-java.lang.String:A-)