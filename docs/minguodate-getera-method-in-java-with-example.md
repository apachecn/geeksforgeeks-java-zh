# Java 中的 MinguoDate getEra()方法搭配示例

> 原文:[https://www . geesforgeks . org/mingodate-getera-method-in-Java-with-example/](https://www.geeksforgeeks.org/minguodate-getera-method-in-java-with-example/)

**Java . time . chrono . mingodate**类的 **getEra()** 方法用于检索与此 mingodate 相关的纪元。

**语法:**

```java
public MinguoEra getEra()

```

**参数**:此方法不接受任何参数。

**返回值**:此方法返回此民国日期的时代。

以下是举例说明 **getEra()** 方法:

T4】例 1:

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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.now();

            // getting chronology of this date
            // by using getEra() method
            MinguoEra crono = hidate.getEra();

            // display the result
            System.out.println("MinguoEra: "
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
MinguoEra: ROC

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
            // MinguoDate Object
            MinguoDate hidate = MinguoDate.of(2008, 04, 24);

            // getting chronology of this date
            // by using getEra() method
            MinguoEra crono = hidate.getEra();

            // display the result
            System.out.println("MinguoEra: "
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
MinguoEra: ROC

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/time/chrono/minguodate . html # getEra–](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/MinguoDate.html#getEra--)