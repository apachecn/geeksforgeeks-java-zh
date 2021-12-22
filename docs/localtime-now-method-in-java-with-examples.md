# Java 中的 LocalTime now()方法，示例

> 原文:[https://www . geesforgeks . org/local time-now-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-now-method-in-java-with-examples/)

Java 中 **LocalTime** 类的 **now()** 方法用于从默认时区的系统时钟中获取当前时间。

**语法:**

```
public static LocalTime now()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法使用系统时钟和默认时区返回当前**时间**。

下面的程序说明了 Java 中 LocalTime 的 now()方法:

**程序 1:**

```
// Java program to demonstrate
// LocalTime.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of LocalTime class
        LocalTime time = LocalTime.now();

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**Output:** It varies as the time passes.

```
Time: 20:43:41.453

```

**程序 2:**

```
// Java program to demonstrate
// LocalTime.now() method

import java.time.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] args)
    {

        // apply now() method
        // of LocalTime class
        LocalTime time = LocalTime.now();

        // print time
        System.out.println("Time: "
                           + time);
    }
}
```

**Output:** It varies as the time passes.

```
Time: 20:44:06.567

```

上面两个例子显示了同一程序的输出是如何随着时间的推移而变化的。
**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local time . html # now()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#now())