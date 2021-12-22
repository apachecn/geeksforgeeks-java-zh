# Java 中的 minuodate getserratory()方法，示例

> 原文:[https://www . geeksforgeeks . org/Minguo date-getserial-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-getchronology-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的**get 年代学()**方法用于检索该日期所属的该民国日期的年代学。

**语法:**

```java
public MinguoChronology getChronology()

```

**参数**:此方法不接受任何参数。

**返回值**:这个方法返回这个民国日期的年表。

以下是举例说明**从()**法:

T4】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getChronology() method

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
            MinguoDate hidate = MinguoDate.now();

            // getting chronology of this date
            // by using getChronology() method
            MinguoChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("MinguoChronology: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
MinguoChronology: Minguo

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getChronology() method

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
            MinguoDate hidate = MinguoDate.of(2008, 04, 24);

            // getting chronology of this date
            // by using getChronology() method
            MinguoChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("MinguoChronology: "
                               + crono);
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
MinguoChronology: Minguo

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # GetError–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#getChronology--)