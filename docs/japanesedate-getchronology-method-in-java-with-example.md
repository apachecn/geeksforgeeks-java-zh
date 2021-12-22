# Java 中的 JapaneseDate 年表()方法，示例

> 原文:[https://www . geeksforgeeks . org/japanesedate-get timer-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-getchronology-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的**get 年代学()**方法用于检索这个日期所在的这个日本日期的年代学。

**语法:**

```java
public JapaneseChronology getChronology()

```

**参数**:此方法不接受任何参数。
**返回值:**这个方法返回这个日本日期的年表。

以下是说明**获取时间表()**方法的示例:

**例 1:**

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
            // JapaneseDate Object
            JapaneseDate hidate = JapaneseDate.now();

            // getting chronology of this date
            // by using getChronology() method
            JapaneseChronology crono
                = hidate.getChronology();

            // display the result
            System.out.println("JapaneseChronology: "
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

**Output**

```java
JapaneseChronology: Japanese

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
  public static void main(String[] argv) {
    try {
      // creating and initializing
      // JapaneseDate Object
      JapaneseDate hidate
        = JapaneseDate.of(2008, 04, 24);

      // getting chronology of this date
      // by using getChronology() method
      JapaneseChronology crono
        = hidate.getChronology();

      // display the result
      System.out.println(
        "JapaneseChronology: "
        + crono);
    } catch (DateTimeException e) {
      System.out.println(
        "passed parameter can"
        + " not form a date");
      System.out.println(
        "Exception thrown: " + e);
    }
  }
}
```

**Output**

```java
JapaneseChronology: Japanese

```

**参考:**