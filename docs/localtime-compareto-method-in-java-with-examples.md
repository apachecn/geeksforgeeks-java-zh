# Java 中的 LocalTime compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-compareto-method-in-java-with-examples/)

**LocalTime 类**的 **compareTo()** 方法用于将这个 LocalTime 对象与作为参数传递的 LocalTime 进行比较，以检查两个 LocalTime 是否相等。两个本地时间之间的比较基于一天内本地时间的时间线位置。该方法返回的值确定如下:

*   If the LocalTime is greater than the LocalTime passed as a parameter, a positive value is returned.
*   If the LocalTime is equal to the LocalTime passed as a parameter, it returns zero (0)
*   If the LocalTime is less than the LocalTime passed as a parameter, a negative value is returned.

**语法:**

```
public int compareTo(LocalTime other)

```

**参数:**该方法接受单个参数 **LocalTime** ，即要比较的另一个 LocalTime，不应该为空。

**返回值:**该方法返回**整数值**，返回值确定如下:

*   如果此 LocalTime 大于作为参数传递的 LocalTime，则返回正值
*   如果这个本地时间等于作为参数传递的本地时间，则返回零(0)
*   如果此本地时间小于作为参数传递的本地时间，则返回负值。

下面的程序说明了 compareTo()方法:

**程序 1:** 当该本地时间大于

```
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("17:52:49");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**时，输出:**

```
Int Value:1
LocalTime1 is greater

```

**程序 2:** 通过时本地时间大于

```
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("07:12:29");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**输出:**

```
Int Value:-1
LocalTime2 is greater

```

**程序 3:** 当两个本地时间相等时

```
// Java program to demonstrate
// LocalTime.compareTo() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1
            = LocalTime.parse("13:08:00");
        LocalTime time2
            = LocalTime.parse("13:08:00");

        // apply compareTo()
        int value = time1.compareTo(time2);

        // print LocalDateTime
        System.out.println("Int Value:" + value);

        if (value > 0)
            System.out.println("LocalTime1 is greater");
        else if (value == 0)
            System.out.println("LocalTime1 is equal to"
                               + " LocalTime2");
        else
            System.out.println("LocalTime2 is greater");
    }
}
```

**输出:**

```
Int Value:0
LocalTime1 is equal to LocalTime2

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # compare to(Java . time . local time))](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#compareTo(java.time.LocalTime))