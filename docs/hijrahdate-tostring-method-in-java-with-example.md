# Java 中的 HijrahDate toString()方法，示例

> 原文:[https://www . geesforgeks . org/hijrahdate-tostring-method-in-Java-with-example/](https://www.geeksforgeeks.org/hijrahdate-tostring-method-in-java-with-example/)

类的 **toString()** 方法用于将 hijrah 日期表示为字符串格式。
**语法:**

```
public String toString()
```

**参数**:该方法不接受任何参数作为参数。
**返回值:**该方法将**回历日期**返回为字符串格式。
以下是举例说明 **toString()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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

            // Getting string representation
            // of hijrah date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Hijrahdate : "
                               + date);
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
Hijrahdate : Hijrah-umalqura AH 1441-06-25
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

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
            HijrahDate hidate = HijrahDate.of(1345, 05, 23);

            // Getting string representation
            // of hijrah date
            // by using toString() method
            String date = hidate.toString();

            // Display the result
            System.out.println("Hijrahdate : "
                               + date);
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
Hijrahdate : Hijrah-umalqura AH 1345-05-23
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/hijrahdate . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/HijrahDate.html#toString--)