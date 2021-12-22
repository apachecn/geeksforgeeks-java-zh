# Java 中的等时技术 eraOf()方法，示例

> 原文:[https://www . geesforgeks . org/isochronomics-eraof-method-in-Java-with-example/](https://www.geeksforgeeks.org/isochronology-eraof-method-in-java-with-example/)

**Java . time . chrono . IsoChronology**类的 **eraOf()** 方法用于通过使用数值 0 和 1 来检索 Iso Era，因为 isochronology 只包含两个 HijrahEra。

**语法:**

```java
public IsoEra eraOf(int eraValue)
```

**参数**:该方法将**误差值**整数作为生成等熵线的参数。

**返回值:**该方法通过使用数值 0 和 1 返回 **Iso Era** ，因为 IsoCronology 只包含两个 HijrahEra。

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting IsoEra for the
            // given integer value
            // by using eraOf() method
            IsoEra era = crono.eraOf(0);

            // display the result
            System.out.println("IsoEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
IsoEra is: BCE

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
            // LocalDate Object
            LocalDate hidate = LocalDate.now();

            // getting IsoChronology
            // used in LocalDate
            IsoChronology crono
                = hidate.getChronology();

            // getting IsoEra for the
            // given integer value
            // by using eraOf() method
            IsoEra era = crono.eraOf(1);

            // display the result
            System.out.println("IsoEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println("HijrahEra is invalid");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
IsoEra is: CE

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/isochronomics . html # eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/IsoChronology.html#eraOf-int-)