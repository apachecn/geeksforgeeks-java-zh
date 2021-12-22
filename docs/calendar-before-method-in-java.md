# Java 中的 Calendar.before()方法

> 原文:[https://www . geesforgeks . org/calendar-before-in-method-Java/](https://www.geeksforgeeks.org/calendar-before-method-in-java/)

java.util.Calendar.before()是 java.util 包的 **Calendar** 类中的一个方法。当对象出现时，如果本日历所代表的时间在**所代表的时间之前，则方法返回*真*。如果不是，则返回*假*。**

**语法:**

```java
public boolean before(Object when)

Where, when is the Object 
that is to be compared.

```

下面是一些例子，可以更好地理解 Calendar.before()函数的实现。

**例 1 :**

```java
// Implementation to show the usage
// of before(Object when) method of
// Calendar class
import java.util.*;

class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {

        // creating calendar object
        Calendar cal_obj1 = Calendar.getInstance();

        // printing current date
        System.out.println("Time 1 : " + cal_obj1.getTime());

        // sleep for 3 seconds
        Thread.sleep(3000);

        // creating Calendar object
        Calendar cal_obj2 = Calendar.getInstance();

        // printing current date
        System.out.println("Time 2 : " + cal_obj2.getTime());

        // checking if 1st date is before 2nd date
        // and printing the result
        System.out.println(cal_obj1.before(cal_obj2));
    }
}
```

输出:

```java
Time 1 : Wed Feb 28 15:43:19 IST 2018
Time 2 : Wed Feb 28 15:43:22 IST 2018
true

```

**例 2 :**

```java
// Implementation to show the usage
// of before(Object when) method of
// Calendar class
import java.util.*;

class GFG {

    public static void main(String[] args)
    {

        // creating calendar objects
        Calendar cal_obj1 = Calendar.getInstance();
        Calendar cal_obj2 = Calendar.getInstance();

        // displaying the current date
        System.out.println("Current date is : " + cal_obj1.getTime());

        // changing year in cal_obj2 calendar
        cal_obj2.set(Calendar.YEAR, 2010);

        // displaying the year
        System.out.println("Year is " + cal_obj2.get(Calendar.YEAR));

        // check if calendar date is before current date
        System.out.println("Result : " + cal_obj1.before(cal_obj2));
    }
}
```

输出:

```java
Current date is : Wed Feb 28 15:50:16 IST 2018
Year is 2010
Result : false

```

**例 3 :**

```java
// Implementation to show the usage
// of before(Object when) method of
// Calendar class
import java.util.*;

class GFG {

    public static void main(String[] args)
    {

        // creating calendar objects
        Calendar cal_obj1 = Calendar.getInstance();
        Calendar cal_obj2 = Calendar.getInstance();

        // displaying the current date
        System.out.println("Current date is : " + cal_obj1.getTime());

        // changing year in cal_obj2 calendar
        cal_obj2.set(Calendar.YEAR, 2025);

        // displaying the year
        System.out.println("Year is " + cal_obj2.get(Calendar.YEAR));

        // check if calendar date is before current date
        System.out.println("Result : " + cal_obj1.before(cal_obj2));
    }
}
```

输出:

```java
Current date is : Wed Feb 28 16:15:55 IST 2018
Year is 2025
Result : true

```