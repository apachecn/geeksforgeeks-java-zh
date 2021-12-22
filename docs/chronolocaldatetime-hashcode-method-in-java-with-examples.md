# Java 中的 chronolocaltimehashcode()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronolocaldatetime-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronolocaldatetime-hashcode-method-in-java-with-examples/)

Java 中**chronolocaldetime**接口的 **hashCode()** 方法用来获取这个 chronolocaldetime 对象的 hashCode 值。

**语法** :

```
int hashCode()

```

**参数**:该方法不接受任何参数。

**返回值**:返回一个**整数值**，这是这个 ChronoLocalDateTime 对象的 hashCode 值。

下面的程序说明了 Java 中的 ChronoLocalDateTime 的 hashCode()方法:

**程序 1** :

```
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime
                  .parse("2018-12-06T19:21:12");

        System.out.println(dt);

        // Get the hashCode value
        System.out.println("Hashcode: "
                           + dt.hashCode());
    }
}
```

**输出:**

```
2018-12-06T19:21:12
Hashcode: -957301669

```

**程序二** :

```
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;
import java.time.chrono.*;

public class GfG {
    public static void main(String[] args)
    {
        // First date
        ChronoLocalDateTime dt
            = LocalDateTime
                  .parse("2018-12-05T19:21:12");

        System.out.println(dt);

        // Get the hashCode value
        System.out.println("Hashcode: "
                           + dt.hashCode());
    }
}
```

**输出:**

```
2018-12-05T19:21:12
Hashcode: -957301672

```

**参考**:[https://docs . Oracle . com/javae/9/docs/API/Java/time/cron/chrolcaldatetime . html # hashcode】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoLocalDateTime.html#hashCode--)