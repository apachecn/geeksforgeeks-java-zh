# Java 中的日本年表 eraOf()方法，示例

> 原文:[https://www . geeksforgeeks . org/Japanese 年表-java 中的 eraof-method-with-example/](https://www.geeksforgeeks.org/japanesechronology-eraof-method-in-java-with-example/)

**Java . time . chrono . Japanese 年表**类的 **eraOf()** 方法用于通过使用数值来检索 JapaneseEra。

**语法:**

```
public JapaneseEra eraOf(int eraValue)
```

**参数**:该方法将**整数值**作为将要生成日本种子的参数。

**返回值:**该方法使用数值返回**日本时代**。

以下是举例说明 **eraOf()** 方法的例子:

**例 1:**

```
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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseEra for the
            // given integer value
            // by using eraOf() method
            JapaneseEra era = crono.eraOf(0);

            // display the result
            System.out.println(
                "JapaneseEra is: "
                + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
JapaneseEra is: Taisho

```

**例 2:**

```
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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // getting JapaneseChronology
            // used in LocalDate
            JapaneseChronology crono
                = hidate.getChronology();

            // getting JapaneseEra for the
            // given integer value
            // by using eraOf() method
            JapaneseEra era = crono.eraOf(2);

            // display the result
            System.out.println("JapaneseEra is: "
                               + era);
        }
        catch (DateTimeException e) {
            System.out.println(
                "JapaneseEra is invalid");
            System.out.println(
                "Exception thrown: " + e);
        }
    }
}
```

**输出:**

```
JapaneseEra is: Heisei

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/Japanese seriogram . html # eraOf-int-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseChronology.html#eraOf-int-)