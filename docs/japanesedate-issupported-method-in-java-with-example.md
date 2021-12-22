# JapaneseDate isSupported()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/japanesedate-issupported-method-in-Java-with-example/](https://www.geeksforgeeks.org/japanesedate-issupported-method-in-java-with-example/)

**Java . time . chrono . japanesedate**类的 **isSupported()** 方法用于检查特定的 chrono 字段是否被支持。

**语法:**

```java
public boolean isSupported(TemporalField field)
```

**参数**:该方法接受计时字段的类型，以检查其是否与特定日期兼容。

**返回值:**如果该日期与传递的字段兼容，则该方法返回布尔值，否则返回真或假。

下面是举例说明 **hashCode()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate
// isSupported() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate = JapaneseDate.now();

            // checking for the
            // given ChronoField
            // by using isSupported() method
            boolean status = hidate.isSupported(
                ChronoField.ERA);

            // display the result
            if (status)
                System.out.println(
                    "this field is supported");
            else
                System.out.println(
                    "this field is not supported");
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
this field is supported

```

**例 2:**

```java
// Java program to demonstrate
// isSupported() method

import java.util.*;
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.temporal.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing
            // JapaneseDate Object
            JapaneseDate hidate = JapaneseDate.now();

            // checking for the
            // given ChronoField
            // by using isSupported() method
            boolean status = hidate.isSupported(
                ChronoField.MICRO_OF_DAY);

            // display the result
            if (status)
                System.out.println(
                    "this field is supported");
            else
                System.out.println(
                    "this field is not supported");
        }
        catch (DateTimeException e) {
            System.out.println("passed parameter can"
                               + " not form a date");
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**输出:**

```java
this field is not supported

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/japanesedate . html # isSupported-Java . time . temporal field-](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/JapaneseDate.html#isSupported-java.time.temporal.TemporalField-)