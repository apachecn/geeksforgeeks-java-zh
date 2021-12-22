# Java 中的 min 国 Date lengthOfMonth()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo date-length of month-in-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-lengthofmonth-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **lengthOfMonth()** 方法用于获取特定的 mingodate 表示的一个月中的天数。

**语法:**

```
public int lengthOfMonth()

```

**参数**:该方法不接受任何参数作为参数。

**返回值**:这个方法返回一个月中某个特定的民国日期所代表的天数。

以下是举例说明 **lengthOfMonth()** 方法:

T4】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// lengthOfMonth() method

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
            MinguoDate hidate
                = MinguoDate.now();

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

            // Display the result
            System.out.println("no of day present: "
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
no of day present: 30

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// lengthOfMonth() method

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
            MinguoDate hidate
                = MinguoDate.of(2020, 06, 23);

            // Getting length of a month
            // by using lengthOfMonth() method
            int length = hidate.lengthOfMonth();

            // Display the result
            System.out.println("no of day present: "
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
no of day present: 30

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # length of month–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#lengthOfMonth--)