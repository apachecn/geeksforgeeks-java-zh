# Java 中的 MinguoDate toEpochDay()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo date-toepochday-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-toepochday-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的**to pochday()**方法用于获取当前民国日期和 0059-01-01 之间存在的纪元天数。

**语法:**

```
public long toEpochDay()
```

**参数**:该方法不接受任何参数作为参数。

**返回值:**此方法返回当前民国日期和 0059-01-01 之间存在的**历元天数**

以下是举例说明**to pochday()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

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

```
EpochDay : 18379

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.of(59, 01, 01);

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

```
EpochDay : 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # toEpochDay–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#toEpochDay--)