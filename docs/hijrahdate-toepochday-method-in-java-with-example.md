# Java 中的 HijrahDate toEpochDay()方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrahdate-toepochday-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-toepochday-method-in-java-with-example/)

**Java . time . chrono . hijrahdate**类的 **toEpochDay()** 方法用于获取当前 Hijrah 日期和 1389-10-22 之间存在的纪元天数。

**语法:**

```java
public long toEpochDay()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**此方法返回当前回历日期和 1389-10-22 之间存在的**纪元天数**。

以下是举例说明**to pochday()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toEpochDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate = HijrahDate.now();

            // Getting no of ephoch days present
            // by using toEpochDay() method
            long length = hidate.toEpochDay();

            // Display the result
            System.out.println("EpochDay : "
                               + length);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```java
EpochDay : 18311

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// toEpochDay() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // Creating and initializing
            // HijrahDate Object
            HijrahDate hidate
                = HijrahDate.of(1389, 10, 22);

            // Getting no of ephoch days present
            // by using toEpochDay() method
            long length = hidate.toEpochDay();

            // Display the result
            System.out.println("EpochDay : "
                               + length);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: "
                               + e);
        }
    }
}
```

**Output:**

```java
EpochDay : 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # toEpochDay–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#toEpochDay--)