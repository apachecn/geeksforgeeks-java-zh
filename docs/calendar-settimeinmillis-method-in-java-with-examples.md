# Java 中的 Calendar setTimeInMillis()方法，带示例

> 原文:[https://www . geeksforgeeks . org/calendar-settimeinmillis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-settimeinmillis-method-in-java-with-examples/)

Calendar 类中的**setTimeInMillis(long*mill _ sec*)**方法用于根据传递的 long 值设置此 Calendar 表示的 Calendar 时间。

**语法:**

```
public void setTimeInMillis(long *mill_sec*)
```

**参数:**该方法取长数据类型的一个参数 **mill_sec** ，指的是要设置的给定日期。

**返回值:**该方法不返回值。

以下程序说明了日历类 setTimeInMillis()方法的工作:
**示例 1:**

```
// Java code to illustrate
// setTimeInMillis() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Getting the time in milliseconds
        System.out.println("The Current"
                           + " Time is: "
                           + calndr.getTime());

        // Changing time to 2000 milli-second
        calndr.setTimeInMillis(2000);

        // Displaying the new time
        System.out.println("After setting"
                           + " Time: "
                           + calndr.getTime());
    }
}
```

**Output:**

```
The Current Time is: Fri Feb 22 08:00:54 UTC 2019
After setting Time: Thu Jan 01 00:00:02 UTC 1970

```

**例 2:**

```
// Java code to illustrate
// setTimeInMillis() method

import java.util.*;

public class Calendar_Demo {
    public static void main(String args[])
    {

        // Creating calendar object
        Calendar calndr = Calendar.getInstance();

        // Getting the time in milliseconds
        System.out.println("The Current"
                           + " Time is: "
                           + calndr.getTime());

        // Changing time to 8000 milli-second
        calndr.setTimeInMillis(8000);

        // Displaying the new time
        System.out.println("After setting"
                           + " Time: "
                           + calndr.getTime());
    }
}
```

**Output:**

```
The Current Time is: Fri Feb 22 08:01:02 UTC 2019
After setting Time: Thu Jan 01 00:00:08 UTC 1970

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/calendar . html # setTimeInMillis(长)](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html#setTimeInMillis(long))