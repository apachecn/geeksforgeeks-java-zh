# Java 中的 LocalTime minusMinutes()方法，示例

> 原文:[https://www . geesforgeks . org/local time-mins minutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-minusminutes-method-in-java-with-examples/)

**LocalTime 类**的**minutations()**方法用于从该 LocalTime 中减去指定的分钟数值，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```
public LocalTime minusMinutes(long MinutesToSubtract)

```

**参数:**该方法接受单个参数**分钟减去**，即要减去的分钟值，可以是负值。

**返回值:**该方法根据该时间减去分钟数返回**当地时间**。

下面的程序说明了 minusMinutes()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.minusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before subtraction: "
                           + time);

        // subtract 55 Minutes using minusMinutes()
        LocalTime value = time.minusMinutes(55);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```
LocalTime before subtraction: 19:34:50.630
LocalTime after subtraction: 18:39:50.630

```

**程序二:**

```
// Java program to demonstrate
// LocalTime.minusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before subtraction: "
                           + time);

        // subtract 600 Minutes using minusMinutes()
        LocalTime value = time.minusMinutes(600);

        // print result
        System.out.println("LocalTime after subtraction: "
                           + value);
    }
}
```

**输出:**

```
LocalTime before subtraction: 01:00:01
LocalTime after subtraction: 15:00:01

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # minutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#minusMinutes(long))