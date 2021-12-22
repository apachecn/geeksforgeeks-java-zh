# java 中的 java.time.Instant 类

> 原文:[https://www . geesforgeks . org/Java-time-instant-class-in-Java/](https://www.geeksforgeeks.org/java-time-instant-class-in-java/)

在 Java 语言中，**即时类**用于表示当前时间轴上的特定时间瞬间。即时类扩展了**对象类**，实现了**可比接口**。

**即时类申报**

```
public final class Instant extends Object    
implements Temporal, TemporalAdjuster, Comparable<Instant>, Serializable  
```

**类的字段:**

<figure class="table">

| **场** | **描述** |
| --- | --- |
| 世 | 1970-01-01T00:00:00Z 纪元瞬间的常数。 |
| 马克斯(男子名ˌ等于 Maximilian) | 支持的最大即时消息，“10000000000-12-31t 23:59:59.99999999999 z”。 |
| 部 | 支持的最小即时，'-1000000000-01-01T00:00Z '。 |

</figure>

**该类方法:**

<figure class="table">

| **方法** | 

**描述**

 |
| --- | --- |
| 调整(暂时的) | 此方法调整指定的时间对象以具有这一瞬间。 |
| 区域位移(ZoneOffset) | 这个方法将这个瞬间和一个偏移量结合起来，创建一个偏移量日期时间。 |
| 集区(ZoneId zone) | 这个方法将这个瞬间和一个时区结合起来创建一个 ZonedDateTime。 |
| 共享(即时他人) | 此方法将此瞬间与指定的瞬间进行比较。 |
| 等于(对象其他即时) | 此方法检查该瞬间是否等于指定的瞬间。 |
| 来自(临时过程或临时) | 此方法从时态对象获取 Instant 的实例。 |
| get(临时字段) | 此方法以 int 形式获取当前指定字段的值。 |
| getEpochSecond() | 此方法从 1970-01-01T00:00:00Z 的 Java 纪元中获取秒数。 |
| getLong(临时字段) | 此方法从此时开始获取指定字段的值。 |
| getNano() | 这个方法从第二个开始获取纳秒数，稍后沿着时间线。 |
| hashCode() | 此方法返回当前时刻的哈希代码。 |
| isafter(即时他人) | 此方法检查该时刻是否在指定时刻之后。 |
| isbefore(即时他人) | 此方法检查该时刻是否在指定时刻之前。 |
| 问题支持(临时字段) | 此方法检查指定的字段是否受支持。 |
| 发行支持(临时单位) | 此方法检查指定的单元是否受支持。 |
| 减(长量到子体积，时间单位) | 此方法返回减去指定数量后的该瞬间的副本。 |
| 减(临时金额到小计) | 此方法返回减去指定数量后的该瞬间的副本。 |
| 毫秒(长毫秒减去) | 此方法返回此瞬间的副本，并减去以毫秒为单位的指定持续时间。 |
| 纳米立方体(长纳米立方体) | 此方法返回此瞬间的副本，并减去以纳秒为单位的指定持续时间。 |
| 负秒(长秒减去) | 此方法返回该瞬间的副本，并减去以秒为单位的指定持续时间。 |
| 现在() | 该方法从系统时钟获得当前时刻。 |
| 现在(时钟) | 此方法从指定的时钟获取当前时刻。 |
| ofpocmilli(long eposchmielli) | 此方法使用 1970-01-01T00:00:00Z 纪元中的毫秒获取 Instant 的实例。 |
| 每秒钟(长时间) | 此方法使用 1970-01-01T00:00:00Z 的纪元中的秒来获取 Instant 的实例。 |
| 十亿秒(长时间的十亿秒，长时间的纳米调整) | 此方法使用 1970-01-01T00:00:00Z 的历元和纳秒级的秒来获取 Instant 的实例。 |
| 解析(字符序列文本) | 此方法从文本字符串(如 2007-12-03T10:15:30.00Z)中获取 Instant 的实例 |
| 加(long amountToAdd，temporalunit unit) | 此方法返回添加了指定数量的即时副本。 |
| amounttoadd 临时挂载) | 此方法返回添加了指定数量的即时副本。 |
| 多毫秒(长毫秒) | 此方法返回此瞬间的副本，并添加以毫秒为单位的指定持续时间。 |
| 纳秒(长纳秒) | 此方法返回此瞬间的副本，并添加以纳秒为单位的指定持续时间。 |
| 多秒(长秒添加) | 此方法返回此瞬间的副本，并添加以秒为单位的指定持续时间。 |
| 查询(临时查询<r>查询)</r> | 此方法使用指定的查询来查询该时刻。 |
| 范围(临时字段) | 此方法获取指定字段的有效值范围。 |
| toEpochMilli() | 此方法将此瞬间转换为从 1970-01-01T00:00:00Z 的纪元开始的毫秒数。 |
| toString() | 使用国际标准化组织 8601 表示法的本瞬间的字符串表示法。 |
| 截断至(时间单位) | 此方法返回被截断为指定单位的即时副本。 |
| 直到(临时结束，临时单位) | 该方法根据指定的单位计算到另一个时刻的时间。 |
| 带(临时调节器) | 此方法返回此瞬间的调整副本。 |
| 带(临时字段，长新值) | 此方法返回指定字段设置为新值的该时刻的副本。 |

</figure>

**示例:**

下面的示例显示了与类相关联的不同方法是如何工作的

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.time.*;
import java.time.temporal.*;
public class GFG {
    public static void main(String[] args)
    {
        // Parsing a string sequence to Instant
        Instant inst1 = Instant.parse("2021-02-09T11:19:42.12Z");
        System.out.println("Parsed instant is " + inst1);

        // Using isSupported() method to check whether the
        // specified field is supported or not
        System.out.println(inst1.isSupported(ChronoUnit.DAYS));
        System.out.println(inst1.isSupported(ChronoUnit.YEARS));

        // Using Instant.now() to get current instant
        Instant cur = Instant.now();
        System.out.println("Current Instant is " + cur);

        // Using minus() method to find instant value after
        // subtraction
        Instant diff = inst1.minus(Duration.ofDays(70));
        System.out.println("Instant after subtraction : "+ diff);

        // Using plus() method to find instant value after
        // addition
        Instant sum = inst1.plus(Duration.ofDays(10));
        System.out.println("Instant after addition : "+ sum);
    }
}
```

**Output**

```
Parsed instant is 2021-02-09T11:19:42.120Z
true
false
Current Instant is 2021-03-03T16:27:54.378693Z
Instant after subtraction : 2020-12-01T11:19:42.120Z
Instant after addition : 2021-02-19T11:19:42.120Z
```