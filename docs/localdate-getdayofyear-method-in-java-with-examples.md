# Java 中的 LocalDate getDayOfYear()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-getdayofyear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-getdayofyear-method-in-java-with-examples/)

Java 中 LocalDate 类的 getDayOfYear()方法获取一年中的某一天字段。

**语法** :

```java
public int getDayOfYear()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数根据闰年的不同，返回在[1，365/366]范围内的日期。

下面的程序说明了 Java 中 LocalDate 的 **getDayOfYear()** 方法:

**程序 1** :

```java
// Program to illustrate the getDayOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the day number
        System.out.println(dt.getDayOfYear());
    }
}
```

**输出:**

```java
331

```

**程序二** :

```java
// Program to illustrate the getDayOfYear() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-01-02");

        // Prints the day number
        System.out.println(dt.getDayOfYear());
    }
}
```

**输出:**

```java
2

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # getDayOfYear()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#getDayOfYear())