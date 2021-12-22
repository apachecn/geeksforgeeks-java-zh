# Java 中的日语日期减(长，临时)方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-mins long-tempalalunit-method-in-Java-with-examples/](https://www.geeksforgeeks.org/japanesedate-minuslong-temporalunit-method-in-java-with-examples/)

**Java . time . chrono . japanesedate**类的**减()**方法用于在从当前日语日期中减去一定数量的时间访问器单位后获得日语日期。
**语法:**

```
public JapaneseDate minus(long amountToAdd,
                          TemporalUnit unit)
```

**参数**:该方法以下列参数为参数:

*   **amountToSubtract:** 是将从当前日本日期中减去的时间单位值。
*   **单位:**是时间单位或时辰单位的对象。

**返回值:**此方法在从当前日本日期中减去一个时间访问器单位后，返回**日本日期**。
以下是举例说明**减()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate minus() method

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
            // JapaneseDate Object
            JapaneseDate hidate
                = JapaneseDate.now();

            // Display the result
            System.out.println("old japanese date: "
                               + hidate);

            // Subtracting japanese date
            // by using minus() method
            JapaneseDate newdate
                = hidate.minus(
                    22, ChronoUnit.DAYS);

            // Display the result
            System.out.println("new japanese date: "
                               + newdate);
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
old japanese date: Japanese Heisei 32-03-23
new japanese date: Japanese Heisei 32-03-01
```