# Java 中的 Calendar getDisplayName()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-getdisplayname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-getdisplayname-method-in-java-with-examples/)

Calendar 类的**getDisplayName(int*cal _ field*、int *cal_style* 、Locale *local* )** 方法用于返回给定样式(int cal_style)和区域设置(int local)中日历字段(int cal_field)值的字符串表示形式。

**语法:**

```java
public String getDisplayName(int *cal_field*, int *cal_style*, Locale *local*)
```

**参数:**该方法取三个参数:

*   *cal_field* :整数类型，指要进行操作的日历的字段。
*   *cal_style* :这是整数类型，指的是应该应用于字符串表示的样式。
*   *local* :这是 locale 对象类型，指的是代表字符串的 Locale。

**返回值:**该方法要么以传递样式的形式返回给定字段的字符串表示形式，要么如果没有可用的字符串表示形式，则返回 null。

下面的程序说明了日历类的 getDisplayName()方法的工作:
**例 1:**

```java
// Java Code to illustrate
// getDisplayName() Method

import java.util.*;

public class Calendar_Demo_Locale {
    public static void main(String args[])
    {

        // Creating Locale objects class
        Locale first_obj = new Locale("TURKISH", "Turkey");

        Locale sec_obj = new Locale("ENGLISH", "UK");

        // Displaying the objects
        System.out.println("First"
                           + " object is : " + first_obj);
        System.out.println("Second"
                           + " object is : " + sec_obj);

        // Getting the display names
        String obj_nm = first_obj.getDisplayName();

        // Displaying the results
        System.out.println("Name of the"
                           + " first object: " + obj_nm);

        // Getting the display names
        obj_nm = sec_obj.getDisplayName();
        System.out.println("Name of the"
                           + " second object: " + obj_nm);
    }
}
```

**Output:**

```java
First object is : turkish_TURKEY
Second object is : english_UK
Name of the first object: turkish (TURKEY)
Name of the second object: english (UK)

```

**例 2:**

```java
// Java Code to illustrate
// getDisplayName() Method

import java.util.*;

public class Calendar_Demo_Locale {
    public static void main(String args[])
    {

        // Creating Locale objects class
        Locale first_obj = new Locale("RUSSIAN", "Russia");

        Locale sec_obj = new Locale("GERMAN", "Germany");

        // Displaying the objects
        System.out.println("First"
                           + " object is : " + first_obj);
        System.out.println("Second"
                           + " object is : " + sec_obj);

        // Getting the display names
        String obj_nm = first_obj.getDisplayName();

        // Displaying the results
        System.out.println("Name of the"
                           + " first object: " + obj_nm);

        // Getting the display names
        obj_nm = sec_obj.getDisplayName();
        System.out.println("Name of the"
                           + " second object: " + obj_nm);
    }
}
```

**Output:**

```java
First object is : russian_RUSSIA
Second object is : german_GERMANY
Name of the first object: russian (RUSSIA)
Name of the second object: german (GERMANY)

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # getDisplayName(int，%20int，%20java.util.Locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#getDisplayName(int, %20int, %20java.util.Locale))