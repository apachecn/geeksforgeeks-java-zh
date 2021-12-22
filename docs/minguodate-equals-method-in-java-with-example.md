# Java 中的 MinguoDate 等于()方法，示例

> 原文:[https://www . geesforgeks . org/minuodate-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-equals-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **equals()** 方法用于将这个民国日期与另一个民国日期进行比较。

**语法:**

```java
public boolean equals(Object obj)

```

**参数**:该方法以一个等价的**对象**为参数，与该明国号进行比较。

**返回值**:如果两个日期相等，则该方法返回**真**，否则返回**假**。

以下是举例说明**等于()**方法:
T3】例 1:

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate1
                = MinguoDate.now();

            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate2
                = MinguoDate.now();

            // comparing both date
            // by using equals() method
            boolean status
                = hidate1.equals(hidate2);

            // display the result
            if (status)
                System.out.println(
                    "both dates are equal");
            else
                System.out.println(
                    "both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
both dates are equal

```

**例 2:**

```java
// Java program to demonstrate
// equals() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate1
                = MinguoDate.now();

            // creating and initializing
            // MinguoDate Object
            MinguoDate hidate2
                = MinguoDate.of(2008, 03, 23);

            // comparing both date
            // by using equals() method
            boolean status
                = hidate1.equals(hidate2);

            // display the result
            if (status)
                System.out.println(
                    "both dates are equal");
            else
                System.out.println(
                    "both dates are not equal");
        }
        catch (DateTimeException e) {
            System.out.println(
                "passed parameter can"
                + " not form a date");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
both dates are not equal

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#equals-java.lang.Object-)