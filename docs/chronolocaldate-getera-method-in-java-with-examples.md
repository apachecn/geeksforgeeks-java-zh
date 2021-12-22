# Java 中的 ChronoLocalDate getEra()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldata-getera-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldate-getera-method-in-java-with-examples/)

Java 中**ChronalDate**接口的 **getEra()** 方法得到该日期适用的纪元。

**语法** :

```java
public Era getEra()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数返回该日期适用的等时纪元常数，不为空。

下面的程序说明了 Java 中的 **getEra()** 方法:

**程序 1** :

```java
// Program to illustrate the getEra() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getEra());
    }
}
```

**输出:**

```java
CE

```

**程序二** :

```java
// Program to illustrate the getEra() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        ChronoLocalDate dt
            = LocalDate.parse("2018-01-21");

        // Prints the day number
        System.out.println(dt.getEra());
    }
}
```

**输出:**

```java
CE

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chroncaldate . html # getera】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDate.html#getEra--)