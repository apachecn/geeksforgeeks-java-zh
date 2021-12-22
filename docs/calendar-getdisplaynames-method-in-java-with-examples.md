# Java 中的 Calendar getDisplayNames()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-getdisplaynames-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getdisplaynames-method-in-java-with-examples/)

Calendar 类的**getDisplayNames(int*cal _ field*、int *cal_style* 、Locale *local* )** 方法用于返回包含给定样式(int cal_style)和区域设置(Locale local)中日历字段(int cal_field)的所有名称及其对应字段值的映射。

**语法:**

```java
public Map getDisplayNames(*int field, int style, Locale locale*)
```

**参数:**该方法取三个参数:

*   *cal_field* :整数类型，指要进行操作的日历的字段。
*   *cal_style* :这是整数类型，指的是应该应用于字符串表示的样式。
*   *local* :这是 locale 对象类型，指的是代表字符串的 Locale。

**返回值:**该方法要么以传递样式的形式返回给定字段的字符串表示形式，要么如果没有可用的字符串表示形式，则返回 null。

下面的程序说明了日历类的 getDisplayNames()方法的工作:
**示例:**

```java
// Java Code to illustrate
// getdisplaynames() Method

import java.util.*;

public class Calendar_Demo_Locale {
    public static void main(String args[])
    {

        // Creating the Calendar
        Calendar cal = Calendar.getInstance();

        // Creating the Locale
        Locale local = Locale.getDefault();

        // Calling the getdisplaynames method
        Map<String, Integer> cal_repres = cal.getDisplayNames(Calendar.DAY_OF_WEEK,
                                                              Calendar.LONG, local);

        NavigableMap<String, Integer> Nav_Map = new TreeMap<String, Integer>(cal_repres);

        // Displaying the results
        System.out.printf("The complete list is: %n%s%n", Nav_Map);
    }
}
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getDisplayNames(int，%20int，%20java.util.Locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getDisplayNames(int, %20int, %20java.util.Locale))