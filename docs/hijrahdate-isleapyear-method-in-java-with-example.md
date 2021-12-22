# Java 中的 HijrahDate isLeapYear()方法，示例

> 原文:[https://www . geeksforgeeks . org/hijrahdate-islapyear-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-isleapyear-method-in-java-with-example/)

**Java . time . chrono . hijrahdate**类的**islapyear()**方法用于区分闰年和非闰年。如果这个 HijrahDate 代表的年份是闰年，这个方法将返回 true，否则返回 false。

**语法:**

```
public boolean isLeapYear()

```

**参数**:该方法不接受任何参数作为参数。

**返回值:**该方法返回**布尔值**，即如果前一年是闰年则为真，否则为假。

以下是说明**方法的示例:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isLeapYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating and initializing
        // HijrahDate Object
        HijrahDate hidate
            = HijrahDate.of(1398, 03, 23);

        System.out.println("HijrahDate: "
                           + hidate.toString());

        // Checking if the date is leap year or not
        // by using isLeapYear() method
        boolean flag = hidate.isLeapYear();

        // Display the result
        if (flag)
            System.out.println("Leap year");
        else
            System.out.println("Not a leap year");
    }
}
```

**Output:**

```
HijrahDate: Hijrah-umalqura AH 1398-03-23
Not a leap year

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// isLeapYear() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        // Creating and initializing
        // HijrahDate Object
        HijrahDate hidate = HijrahDate.now();

        System.out.println("HijrahDate: "
                           + hidate.toString());

        // Checking if the date is leap year or not
        // by using isLeapYear() method
        boolean flag = hidate.isLeapYear();

        // Display the result
        if (flag)
            System.out.println("Leap year");
        else
            System.out.println("Not a leap year");
    }
}
```

**Output:**

```
HijrahDate: Hijrah-umalqura AH 1441-06-25
Leap year

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # islapyear–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#isLeapYear--)