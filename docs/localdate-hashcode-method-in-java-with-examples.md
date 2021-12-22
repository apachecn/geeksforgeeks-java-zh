# Java 中的 LocalDate hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-hashcode-method-in-java-with-examples/)

Java 中 LocalDate 类的 hashCode()方法获取年份字段。

**语法** :

```java
public int hashCode()

```

**参数**:该方法不接受任何参数。

**返回值**:该函数返回一个合适的哈希码。

下面的程序说明了 Java 中 LocalDate 的 **hashCode()** 方法:

**程序 1** :

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2018-11-27");

        // Prints the hash-code
        System.out.println(dt.hashCode());
    }
}
```

**输出:**

```java
4133595

```

**程序二** :

```java
// Program to illustrate the hashCode() method

import java.util.*;
import java.time.*;

public class GfG {
    public static void main(String[] args)
    {
        // Parses the date
        LocalDate dt = LocalDate.parse("2015-12-23");

        // Prints the hash-code
        System.out.println(dt.hashCode());
    }
}
```

**输出:**

```java
4127511

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#hashCode())