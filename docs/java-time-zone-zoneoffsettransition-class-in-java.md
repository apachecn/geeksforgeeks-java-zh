# java 中的 Java . time . zone . zoneoffsettransition 类

> 原文:[https://www . geesforgeks . org/Java-时区-zoneoffsettransition-Java 中的类/](https://www.geeksforgeeks.org/java-time-zone-zoneoffsettransition-class-in-java/)

两个偏移之间的过渡通常是夏令时转换的结果，不连续性通常是春季的间隙和秋季的重叠，而这又是由本地时间线的不连续性引起的。

ZoneOffsetTransition 的功能是对这两个偏移量之间的转换进行建模。

**注意:**类是不可变的，线程安全的

**方法:**

<figure class="table">

| 

**方法**

 | 

描述

 |
| --- | --- |
| 创建过渡(整年) | 此方法为指定的年份创建一个转换实例。 |
| 的(LocalDateTime transition、offsetbefore、ZoneOffset offsetAfter) | 这是一种静态方法，用于检索前后偏移之间的传输对象 |
| 等于() | 此方法用于比较两个区域偏移转换对象。

 |
| compareTo() | 此方法用于比较两个区域偏移转换对象 |
| hashCode() | 此方法用于检索当前 ZoneOffsetTransition 对象的哈希代码。 |
| getDateTimeAfter() | 此方法返回应用了 after 偏移量的 LocalDateTime 对象。 |
| getDateTimeBefore() | 此方法返回一个应用了之前偏移量的 LocalDateTime 对象。 |
| getDuration() | 此方法返回过渡的持续时间对象。

 |
| getInstant() | 此方法返回应用后偏移量时第一个瞬间的 Instant 对象。 |
| getOffsetAfter() | 此方法在转换后返回 ZoneOffset 对象。 |
| getOffsetBefore() | 此方法在转换后返回 ZoneOffset 对象。 |
| isGap() | 此方法返回当前转换是否表示本地时间线中的间隙。 |
| 等重叠() | 此方法返回当前转换是否表示本地时间线中的重叠。 |
| isvalid offset(zoneoffset zoneoffset) | 此方法检查传递的 ZoneOffset 对象是否有效。即如果区域偏移对象至少在一个点有效，则返回真。如果在偏移之前或之后存在重叠，则传递的区域偏移对象将是有效的对象。 |
| toEpochSecond() | 此方法以历元秒(长值)的形式返回过渡瞬间 |
| toString() | 此方法返回一个描述当前区域偏移转换对象的字符串对象。 |

</figure>

下面是 ZoneOffsetTransition 类的 Java 实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.io.*;
import java.time.*;
import java.time.chrono.*;
import java.time.zone.*;
import java.util.*;

public class GeeksForGeeks {
    public static void main(String args[])
    {

        int year1 = 1996, year2 = 2001;

        // creating the offsets
        ZoneOffset ofSet1 = ZoneOffset.ofTotalSeconds(5);
        ZoneOffset ofSet2 = ZoneOffset.ofTotalSeconds(2);

        // creating two transition zones
        ZoneOffsetTransition z1 = ZoneOffsetTransition.of(
            LocalDateTime.of(year1, 11, 24, 03, 24, 48, 0),
            ofSet1, ofSet2);
        ZoneOffsetTransition z2 = ZoneOffsetTransition.of(
            LocalDateTime.of(year2, 10, 30, 01, 21, 52, 0),
            ofSet1, ofSet2);

        // checking for equality of
        // the two transistion zones.
        boolean ans = z1.equals(z2);
        if (ans)
            System.out.println(
                "The transition zones match!");
        else
            System.out.println(
                "Sorry, the transition zones do not match!");

        // using the getOffsetAfter to find the
        // offsetAfter of a transition zone
        ZoneOffset zone = z1.getOffsetAfter();
        System.out.println(
            "The offsetAfter of the first transition zone is"
            + zone);
    }
}
```

**Output**

```java
Sorry, the transition zones do not match!
The offsetAfter of the first transition zone is+00:00:02
```