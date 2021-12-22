# Java 中的 Minguo 年表 eraOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/minguoberor-eraof-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguochronology-eraof-method-in-java-with-example/)

**Java . time . chrono . Minguo 年表**类的 **eraOf()** 方法用于使用数值检索 MinguoEra。

**语法:**

```java
public MinguoEra eraOf(int eraValue)
```

**参数**:该方法将**误差值**整数作为生成 MinguoEra 的参数。

**返回值:**该方法使用数值返回**民国时代**。

以下是举例说明 **eraOf()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// eraOf() method

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
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in LocalDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoEra for the
            // given integer value
            // by using eraOf() method
            MinguoEra era = crono.eraOf(0);

            // display the result
            System.out.println(
                "MinguoEra is: "
                + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "MinguoEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
MinguoEra is: BEFORE_ROC

```

**例 2:**

```java
// Java program to demonstrate
// eraOf() method

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
            MinguoDate hidate
                = MinguoDate.now();

            // getting MinguoChronology
            // used in LocalDate
            MinguoChronology crono
                = hidate.getChronology();

            // getting MinguoEra for the
            // given integer value
            // by using eraOf() method
            MinguoEra era = crono.eraOf(1);

            // display the result
            System.out.println(
                "MinguoEra is: "
                + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "MinguoEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
MinguoEra is: ROC

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Minguo 年表. html#eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoChronology.html#eraOf-int-)