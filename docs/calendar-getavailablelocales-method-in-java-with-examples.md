# Java 中的 Calendar getAvailableLocales()方法，示例

> 原文:[https://www . geeksforgeeks . org/calendar-getavailable locales-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getavailablelocales-method-in-java-with-examples/)

Calendar 类中的 **clear()** 方法用于返回该类的 getInstance 方法的本地化实例中可用的所有区域设置的数组。

**语法:**

```
public static Locale[] getAvailableLocales()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回本地化实例可用的所有区域设置的数组。

以下程序说明了日历类 getAvailableLocales()方法的工作:
**示例 1:**

```
// Java Code to illustrate
// getAvailableLocales() Method

import java.util.*;

public class Calendar_Demo_Locale {
    public static void main(String args[])
    {

        // Creating a locale object
        Locale loc_arr[] = new Locale[5];

        // Assigning locales to array
        loc_arr = Locale.getAvailableLocales();

        // Displaying the results
        System.out.println("The first "
                           + "five locales are:");

        for (int cnt = 0; cnt < 5; cnt++)
            System.out.println(
                loc_arr[cnt]
                    .getISO3Country());
    }
}
```

**Output:**

```
The first five locales are:

ARE
JOR
SYR
HRV

```

**例 2:**

```
// Java Code to illustrate
// getAvailableLocales() Method

import java.util.*;

public class Calendar_Demo_Locale {
    public static void main(String args[])
    {

        // Creating a locale object
        Locale loc_arr[] = new Locale[20];

        // Assigning locales to array
        loc_arr = Locale.getAvailableLocales();

        // Displaying the results
        System.out.println("The first "
                           + "twenty availables"
                           + " locales are:");

        for (int cnt = 0; cnt < 20; cnt++)
            System.out.println(
                loc_arr[cnt]
                    .getISO3Country());
    }
}
```

**Output:**

```
The first twenty availables locales are:

ARE
JOR
SYR
HRV
BEL
PAN
MLT
VEN

TWN

DNK
PRI
VNM
USA
MNE

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # clone()](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#clone())