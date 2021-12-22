# Java 中的 ChronoZonedDateTime hashCode()方法，带示例

> 原文:[https://www . geeksforgeeks . org/chronozoneddatetime-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronozoneddatetime-hashcode-method-in-java-with-examples/)

**时区数据时间**界面的 **hashCode()** 方法用于获取该时区数据时间的 hashCode。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希相关算法进行一些操作，如[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)、[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)等。也可以用这个唯一的代码搜索一个对象。

**语法:**

```java
default int hashCode()

```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个**整数值**代表一个合适的哈希码。

下面的程序说明了 hashCode()方法:

**程序 1:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.hashCode() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "2018-12-06T19:21:12.123+05:30[Asia/Calcutta]");

        // get hashcode
        int value = zoneddatetime.hashCode();

        // print result
        System.out.println("hashcode:" + value);
    }
}
```

**输出:**

```java
hashcode:1966859253

```

**程序二:**

```java
// Java program to demonstrate
// ChronoZonedDateTime.hashCode() method

import java.time.*;
import java.time.chrono.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a ChronoZonedDateTime object
        ChronoZonedDateTime zoneddatetime
            = ZonedDateTime.parse(
                "1918-10-25T23:12:38.543+02:00[Europe/Paris]");

        // get hashcode
        int value = zoneddatetime.hashCode();

        // print result
        System.out.println("hashcode:" + value);
    }
}
```

**输出:**

```java
hashcode:1110445649

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/time/chrono/chronitoredatetime . html # hashcode】](https://docs.oracle.com/javase/9/docs/api/java/time/chrono/ChronoZonedDateTime.html#hashCode--)