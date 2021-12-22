# Java 中的日历 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/calendar-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-hashcode-method-in-java-with-examples/)

Calendar 类中的 **hashCode()** 方法用于返回该 Calendar 对象的哈希代码。
**语法:**

```
public int hashCode()
```

**参数:**该方法不取任何参数。
**返回值:**该方法返回该日历对象的哈希代码值..
以下程序说明了日历类 hashCode()方法的工作:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// hashCode() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr = Calendar.getInstance();

        // Displaying the current calendar
        System.out.println("The time on"
                           + " Calendar shows: "
                           + calndr.getTime());

        // Getting the hash code
        int hash_code = calndr.hashCode();
        System.out.println("The hash code "
                           + "for this calendar is: "
                           + hash_code);
    }
}
```

**Output:** 

```
The time on Calendar shows: Wed Feb 20 15:55:22 UTC 2019
The hash code for this calendar is: 194416203
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// hashCode() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {
        // Creating a calendar
        Calendar calndr
            = new GregorianCalendar(2018, 6, 10);

        // Displaying the current calendar
        System.out.println("The time on"
                           + " Calendar shows: "
                           + calndr.getTime());

        // Getting the hash code
        int hash_code = calndr.hashCode();
        System.out.println("The hash code "
                           + "for this calendar is: "
                           + hash_code);
    }
}
```

**Output:** 

```
The time on Calendar shows: Tue Jul 10 00:00:00 UTC 2018
The hash code for this calendar is: -2123101761
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # hashCode–T4】