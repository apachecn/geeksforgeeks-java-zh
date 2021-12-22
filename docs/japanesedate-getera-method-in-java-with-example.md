# Java 中的 JapaneseDate getEra()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-getera-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-getera-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的 **getEra()** 方法用于检索与该日本日期相关的纪元。

**语法:**

```java
public JapaneseEra getEra()
```

**参数**:此方法不接受任何参数。

**返回值:**这个方法返回这个日本日期的时代。

以下是举例说明 **getEra()** 方法:
T3】例 1:T5】

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getEra() method

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
            JapaneseDate hidate = JapaneseDate.now();

            // getting chronology of this date
            // by using getChronology() method
            JapaneseEra crono = hidate.getEra();

            // display the result
            System.out.println("JapaneseEra: "
                               + crono);
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

**Output**

```java
JapaneseEra: Heisei

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// getEra() method

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
                = JapaneseDate.of(2008, 04, 24);

            // getting chronology of this date
            // by using getChronology() method
            JapaneseEra crono = hidate.getEra();

            // display the result
            System.out.println("JapaneseEra: "
                               + crono);
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

```java
Some error occured or ide is down,please try again

```

**Output**

```java
JapaneseEra: Heisei
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # getEra–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#getEra--)