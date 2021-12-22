# Java 中的日本日期等于()方法，示例

> 原文:[https://www . geesforgeks . org/japanesedate-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-equals-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的**等于()**方法用于将这个日本日期与另一个日本日期进行比较。

**语法:**

```java
public boolean equals(Object obj)

```

**参数**:该方法以一个等价对象为参数，与该日本日期进行比较。
**返回值:**如果两个日期相等，该方法返回真，否则返回假。

以下是举例说明**等于()**方法:
T3】例 1:

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // JapaneseDate Object
            JapaneseDate hidate1
              = JapaneseDate.now();

            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate2
              = JapaneseDate.now();

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

**Output**

```java
both dates are equal

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

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
            // JapaneseDate Object
            JapaneseDate hidate1
              = JapaneseDate.now();

            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate2
              = JapaneseDate.of(2008, 03, 23);

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

**Output**

```java
both dates are not equal

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#equals-java.lang.Object-)