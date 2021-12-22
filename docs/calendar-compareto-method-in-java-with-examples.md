# Java 中日历比较()方法示例

> 原文:[https://www . geeksforgeeks . org/calendar-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-compareto-method-in-java-with-examples/)

[Calendar 类](https://www.geeksforgeeks.org/calendar-class-in-java-with-examples/)的**add(Calendar*Calendar 2*)**方法用于将该 Calendar 对象的时间值或毫秒偏移量与传递的 Calendar 对象进行比较。

**语法:**

```
public int compareTo(Calendar *Calendar2*)
```

**参数:**该方法取 Calendar 对象类型的一个参数 Calendar2，并引用要与该 Calendar 对象进行比较的对象。

**返回值:**该方法返回一个整数值，可以返回以下任意一个值:

1.  如果传递的参数等于此日历对象，则方法返回 0。
2.  如果此日历对象的时间大于传递的对象，则方法返回 1。
3.  如果此日历对象的时间小于传递的对象，则方法返回-1。

下面的程序说明了 Calendar 类的 compareTo()方法的工作:
**例 1:**

```
// Java Code to illustrate compareTo() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1
            = Calendar.getInstance();

        // Creating another calendar object
        Calendar calndr2
            = new GregorianCalendar(2018, 12, 2);

        // Comparing the time
        int val = calndr1.compareTo(calndr2);

        // Displaying the result of comparison
        System.out.println("First"
                           + " comparison result is: "
                           + val);

        // Comparing the time
        val = calndr2.compareTo(calndr1);

        // Displaying the result of comparison
        System.out.println("Second"
                           + " comparison result is: "
                           + val);
    }
}
```

**Output:**

```
First comparison result is: 1
Second comparison result is: -1

```

**例 2:**

```
// Java Code to illustrate compareTo() Method

import java.util.*;

public class CalendarClassDemo {
    public static void main(String args[])
    {
        // Creating a calendar object
        Calendar calndr1 = Calendar.getInstance();

        // Creating another calendar object
        Calendar calndr2 = Calendar.getInstance();

        // Comparing the time
        int val = calndr1.compareTo(calndr2);

        // Displaying the result of comparison
        System.out.println("The"
                           + " comparison result is: "
                           + val);
    }
}
```

**Output:**

```
The comparison result is: -1

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # compare to(Java . util . calendar)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#compareTo(java.util.Calendar))