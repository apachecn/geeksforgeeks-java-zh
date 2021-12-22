# Java 中的日历集()方法，示例

> 原文:[https://www . geesforgeks . org/calendar-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-set-method-in-java-with-examples/)

日历类中的 **set(int *calndr_field* ，int *new_val* )** 方法用于将 calndr_field 值设置为 new_val。此日历的旧字段被新字段替换。

**语法:**

```java
public void set(int *calndr_field*, int *new_val*)
```

**参数:**该方法取两个参数:

*   **calndr_field** :此为 Calendar 类型，指的是要修改的日历的字段。
*   **new_val** :这是指要替换为的新值。

**返回值:**该方法不返回值。

下面的程序说明了 Calendar 类 set()方法的工作:
**例 1:**

```java
// Java code to illustrate
// set() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Displaying the month
        System.out.println("The Current Month is: "
                           + calndr.get(
                                 Calendar.MONTH));

        // Replacing with a new value
        calndr.set(Calendar.MONTH, 11);

        // Displaying the modified result
        System.out.println("Altered Month is: "
                           + calndr.get(
                                 Calendar.MONTH));
    }
}
```

**Output:**

```java
The Current Month is: 1
Altered Month is: 11

```

**例 2:**

```java
// Java code to illustrate
// set() method

import java.util.*;
public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating a calendar
        Calendar calndr = Calendar.getInstance();

        // Displaying the Year
        System.out.println("The Current year is: "
                           + calndr.get(
                                 Calendar.YEAR));

        // Replacing with a new value
        calndr.set(Calendar.YEAR, 1996);

        // Displaying the modified result
        System.out.println("Altered year is: "
                           + calndr.get(
                                 Calendar.YEAR));
    }
}
```

**Output:**

```java
The Current year is: 2019
Altered year is: 1996

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # set-int-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Calendar.html#set-int-int-)