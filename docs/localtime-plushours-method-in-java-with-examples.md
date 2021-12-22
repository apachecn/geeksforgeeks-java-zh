# Java 中的 LocalTime plusHours()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-plushours-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-plushours-method-in-java-with-examples/)

**本地时间类**的 **plusHours()** 方法用于将指定的小时数值添加到该本地时间，并将结果作为本地时间对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```
public LocalTime plusHours(long hoursToAdd)

```

**参数:**此方法接受单个参数**小时添加**，即要添加的小时值，可以是负值。

**返回值:**该方法返回一个**本地时间**基于该时间加上小时。

下面的程序说明了 plusHours()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.plusHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before addition : "
                           + time);

        // added 3 hours using plusHours()
        LocalTime value = time.plusHours(3);

        // print result
        System.out.println("LocalTime after addition : "
                           + value);
    }
}
```

**输出:**

```
LocalTime before addition : 19:34:50.630
LocalTime after addition : 22:34:50.630

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.plusHours() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before addition : "
                           + time);

        // added -10 hours using plusHours()
        LocalTime value = time.plusHours(-10);

        // print result
        System.out.println("LocalTime after addition : "
                           + value);
    }
}
```

**输出:**

```
LocalTime before addition : 01:00:01
LocalTime after addition : 15:00:01

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # plusHours(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plusHours(long))