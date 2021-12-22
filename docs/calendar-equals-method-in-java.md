# Java 中的 Calendar.equals()方法

> 原文:[https://www . geesforgeks . org/calendar-equals-method-in-Java/](https://www.geeksforgeeks.org/calendar-equals-method-in-java/)

java.util.Calendar.equals()是 java.util 包的 **Calendar** 类中的一个方法。方法将此日历与指定的对象进行比较。如果该对象等于*对象*，则该方法返回*真*。如果不是这样，即两个日历之间的参数有任何差异，则返回*假*。

**语法:**

```
public boolean equals(Object object)

Where, object is the Object 
to be compared with.

```

下面是一些例子，可以更好地理解 Calendar.equals()函数的实现。

**例 1 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to show the use of
// equals() method of Calendar class
import java.util.*;

class GFG {

// Driver code
public static void main(String[] args) 
            throws InterruptedException {

    // creating calendar object
    Calendar cal_obj1 = Calendar.getInstance();
    Calendar cal_obj2 = cal_obj1;

    // printing current date
    System.out.println("Time 1 : " + cal_obj1.getTime());

    // printing current date
    System.out.println("Time 2 : " + cal_obj2.getTime());

    // checking if 1st date is equal to 2nd date
    // and printing the result
    System.out.println(cal_obj1.equals(cal_obj2));
    }
}
```