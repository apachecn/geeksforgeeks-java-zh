# java.util.Calendar.after()方法

> 原文:[https://www.geeksforgeeks.org/java-util-calendar-method/](https://www.geeksforgeeks.org/java-util-calendar-method/)

java.util.Calendar.after()是 java.util 包的 **Calendar** 类中的一个方法。如果此日历表示的时间在对象出现时**表示的时间之后，则该方法返回*真*。如果不是，则返回*假*。**

**语法:**

```
public boolean after(Object when)

Where, when is the Object 
that is to be compared.

```

下面是一些例子，可以更好地理解 Calendar.after()函数的实现:

**例 1 :**

```
// Java code show the usage of
// after() method of Calendar class
import java.util.*;

class GFG {

// Driver code
public static void main(String[] args) 
            throws InterruptedException {

    // creating calendar object
    Calendar cal_obj1 = Calendar.getInstance();

    // printing current date
    System.out.println("Time 1 : " + cal_obj1.getTime());

    // creating Calendar object     
    Calendar cal_obj2 = Calendar.getInstance();

    // printing current date
    System.out.println("Time 2 : " + cal_obj2.getTime());

    // checking if 1st date is after 2nd date
    // and printing the result
    System.out.println(cal_obj1.after(cal_obj2));
    }
}
```

输出:

```
Time 1 : Thu Mar 01 09:26:04 UTC 2018
Time 2 : Thu Mar 01 09:26:04 UTC 2018
false

```

**例 2 :**

```
// Java code to show the usage of
// after() method of Calendar class
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating calendar objects
        Calendar cal_obj1 = Calendar.getInstance();
        Calendar cal_obj2 = Calendar.getInstance();

        // displaying the current date
        System.out.println("Current date is : " + cal_obj1.getTime());

        // changing year in cal_obj2 calendar
        cal_obj2.set(Calendar.YEAR, 2010);

        // check if calendar date is after current date
        System.out.println("Result : " + cal_obj1.after(cal_obj2));
    }
}
```

输出:

```
Current date is : Thu Mar 01 09:27:19 UTC 2018
Result : true

```