# Java 中的日期格式符号设置短月()方法，带示例

> 原文:[https://www . geesforgeks . org/dateformatsymbols-setshortmonths-method in-Java-with-examples/](https://www.geeksforgeeks.org/dateformatsymbols-setshortmonths-method-in-java-with-examples/)

Java 中 **DateFormatSymbols 类**的**set short months(String【】*newShMonth*)**方法是将字符串格式的日历月份的简称设置成一些不同的字符串。例如，“Jan”可以改为“FEB”，“JUN”可以改为“GEEK”等。

**语法:**

```java
public void setShortMonths(String[] *newShMonth*)
```

**参数:**该方法取一个参数 ***newShMonth*** ，该参数是 *[字符串](https://www.geeksforgeeks.org/strings-in-java/)* 类型的数组，指的是现有月份中要替换的新字符串。

**返回值:**该方法以字符串格式返回月份的修改名称。

下面的程序说明了 setShortMonths()方法的使用。
**例 1:**

```java
// Java code to demonstrate setShortMonths()

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
        String[] Days = format.getShortMonths();

        // Displaying the original
        System.out.println("Original: ");

        for (int i = 0; i < Days.length; i++) {
            System.out.println(Days[i] + "  ");
        }

        // Taking an alternative names with
        // additional random strings
        String[] modDays = { "GEEK", "FOR",
                             "GEEK", "DEC",
                             "NOV", "JAN",
                             "FEB" };

        // Setting the default into modified
        format.setShortMonths(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getShortMonths();

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
Jan  
Feb  
Mar  
Apr  
May  
Jun  
Jul  
Aug  
Sep  
Oct  
Nov  
Dec  

Modified: 
GEEK  
FOR  
GEEK  
DEC  
NOV  
JAN  
FEB

```

**例 2:**

```java
// Java code to demonstrate setShortMonths()

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
        String[] Days = format.getShortMonths();

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
        format.setShortMonths(modDays);

        // Displaying the modified string
        String[] modifiedDays
            = format.getShortMonths();

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
Jan  
Feb  
Mar  
Apr  
May  
Jun  
Jul  
Aug  
Sep  
Oct  
Nov  
Dec  

Modified: 
123  
456  
JAN  
FEB  
NOV  
Dec  
May

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/text/dateformatsymbols . html # setshortmoons-Java . lang . string:A-](https://docs.oracle.com/javase/8/docs/api/java/text/DateFormatSymbols.html#setShortMonths-java.lang.String:A-)