# Java 中的 LocalTime 等于()方法，示例

> 原文:[https://www . geesforgeks . org/local time-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-equals-method-in-java-with-examples/)

**LocalTime 类**的 **equals()** 方法用于将这个 LocalTime 对象与作为参数传递的 LocalTime 进行比较，当对象相等时返回 true，否则返回 false。两个本地时间之间的比较基于一天内本地时间的时间线位置。该方法返回的值确定如下:

*   True if two LocalTimes are equal.
*   Returns false if the two instances are not equal.

**语法:**

```
public int equals(Object obj)

```

**参数:**此方法接受单个参数**对象**，即另一个要比较的 LocalTime，不应为空。

**返回值:**该方法返回**整数值**，返回值确定如下:

*   如果两个本地时间相等，则返回 true
*   如果两个实例不相等，则返回 false

下面的程序说明了 equals()方法:

**程序 1:** 当两个物体相等时。

```
// Java program to demonstrate
// LocalTime.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1 = LocalTime.parse("13:08:00");
        LocalTime time2 = LocalTime.parse("13:08:00");

        // print  Values
        System.out.println("LocalTime1: "
                           + time1);
        System.out.println("LocalTime2: "
                           + time2);

        // compare both LocalTimes
        boolean value = time1.equals(time2);

        // print results
        System.out.println("Are both LocalTimes are equal: "
                           + value);
    }
}
```

**输出:**

```
LocalTime1: 13:08
LocalTime2: 13:08
Are both LocalTimes are equal: true

```

**程序 2:** 当两个物体不相等时。

```
// Java program to demonstrate
// LocalTime.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime Objects
        LocalTime time1 = LocalTime.parse("03:18:23");
        LocalTime time2 = LocalTime.parse("13:08:20");

        // print values
        System.out.println("LocalTime1: "
                           + time1);
        System.out.println("LocalTime2: "
                           + time2);

        // compare both LocalTimes
        boolean value = time1.equals(time2);

        // print results
        System.out.println("Are both LocalTimes are equal: "
                           + value);
    }
}
```

**输出:**

```
LocalTime1: 03:18:23
LocalTime2: 13:08:20
Are both LocalTimes are equal: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#equals(java.lang.Object))