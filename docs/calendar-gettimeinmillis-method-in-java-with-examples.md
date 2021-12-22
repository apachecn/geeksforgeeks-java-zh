# Java 中的 Calendar getTimeInMillis()方法示例

> 原文:[https://www . geeksforgeeks . org/calendar-gettimeinmillis-method-in-Java-with-examples/](https://www.geeksforgeeks.org/calendar-gettimeinmillis-method-in-java-with-examples/)

Calendar 类中的 **getTimeInMillis()** 方法用于以毫秒为单位返回此 Calendar 的当前时间。
**语法:**

```
public long getTimeInMillis()
```

**参数:**该方法不取任何参数。
**返回值:**该方法以毫秒为单位返回本日历的当前时间。
以下程序说明了日历类 getTimeInMillis()方法的工作:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// getTimeInMillis() method

import java.util.*;

public class Calendar_Demo {

    public static void main(String args[])
        throws InterruptedException
    {

        // Creating a calendar
        Calendar calndr1 = Calendar.getInstance();

        // Displaying the current time
        System.out.println("The Current Time"
                           + " is: "
                           + calndr1.getTimeInMillis());

        // Adding few delay
        Thread.sleep(10000);

        // Creating another calendar
        Calendar calndr2 = Calendar.getInstance();

        // Displaying the upcoming time
        System.out.println("The Upcoming Time"
                           + " is: "
                           + calndr2.getTimeInMillis());
    }
}
```

**Output:** 

```
The Current Time is: 1550725664034
The Upcoming Time is: 1550725674053
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// getTimeInMillis() method

import java.util.*;

public class Calendar_Demo {

    public static void main(String args[])
        throws InterruptedException
    {

        // Creating a calendar
        Calendar calndr1 = Calendar.getInstance();

        // Displaying the current time
        System.out.println("The Current Time"
                           + " is: "
                           + calndr1.getTimeInMillis());

        // Adding few delay
        Thread.sleep(5000);

        // Creating another calendar
        Calendar calndr2 = Calendar.getInstance();

        // Displaying the upcoming time
        System.out.println("The Upcoming Time"
                           + " is: "
                           + calndr2.getTimeInMillis());
    }
}
```

**Output:** 

```
The Current Time is: 1550725683182
The Upcoming Time is: 1550725688208
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/util/calendar . html # getTimeInMillis–T4】