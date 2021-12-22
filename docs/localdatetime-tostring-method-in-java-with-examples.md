# Java 中的 LocalDateTime toString()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-tostring-method-in-java-with-examples/)

**本地日期时间类**的 **toString()** 方法用于获取该本地日期时间的字符串表示。此方法从对象类派生而来，其行为方式类似。

**语法:**

```
public String toString()
```

**参数:**该方法不取参数。

**返回:**这个方法返回一个**字符串值**，它是这个本地日期时间的字符串表示。

下面的程序说明了 LocalDateTime.toString()方法:

**程序 1:**

```
// Program to illustrate the toString() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt = LocalDateTime.now();

        // Get the String representation of this LocalDateTime
        // using toString() method
        System.out.println(dt.toString());
    }
}
```

**输出:**

```
2018-11-30T10:16:26.939

```

**程序二:**

```
// Program to illustrate the toString() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {

        // Get the LocalDateTime instance
        LocalDateTime dt
            = LocalDateTime
                  .parse("2018-11-03T12:45:30");

        // Get the String representation of this LocalDateTime
        // using toString() method
        System.out.println(dt.toString());
    }
}
```

**输出:**

```
2018-11-03T12:45:30

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#toString())