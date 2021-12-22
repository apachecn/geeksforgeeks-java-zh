# java 中的 java.time.Duration 类

> 原文:[https://www . geesforgeks . org/Java-time-duration-class-in-Java/](https://www.geeksforgeeks.org/java-time-duration-class-in-java/)

持续时间是 Java 时间库中基于值的类。它用于获取基于时间的时间量。这个类是不可变的和线程安全的。本文描述了这个类中的所有方法以及一些使用类方法的基本例子。

这个类实现了 Serializable、compatible<duration>、TemporalAmount 接口。</duration>

**出现在课堂上的领域:**

<figure class="table">

| 田 | 描述 |
| --- | --- |
| 静态持续时间 | 它是零持续时间的常数。 |

</figure>

**类中存在的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| abs() | 此方法返回长度的正副本 |
| addTo(时间) | 此方法将此持续时间添加到指定的时间对象中。 |
| 之间的持续时间(时间开始包括，时间结束排除) | 该方法查找两个时态对象之间的持续时间。 |
| 比较(持续时间其他持续时间) | 此方法将此持续时间与指定的持续时间进行比较。 |
| 除以(长除数) | 此方法返回该持续时间除以指定值的副本。 |
| 等于(对象其他持续时间) | 此方法检查该持续时间是否等于指定的持续时间。 |
| 自(临时金额) | 此方法从时间量中获取持续时间的实例。 |
| 获取(临时单位) | 此方法获取请求单位的值。 |
| getNano() | 此方法获取持续时间内每秒的纳秒数。 |
| getSeconds() | 此方法获取此持续时间内的秒数。 |
| getUnits() | 此方法获取此持续时间支持的单位集。 |
| hashCode() | 这段时间的哈希代码。 |
| isNegative() | 此方法检查该持续时间是否为负，不包括零。 |
| isZero() | 此方法检查该持续时间是否为零长度。 |
| 减(持续时间) | 此方法返回该持续时间的副本，并减去指定的持续时间。 |
| 减(长量到子体积，时间单位) | 此方法返回该持续时间的副本，并减去指定的持续时间。 |
| 天数(长天数减去) | 此方法返回此持续时间的副本，减去标准 24 小时天数中的指定持续时间。 |
| 小时(长小时减去) | 此方法返回该持续时间的副本，并减去以小时为单位的指定持续时间。 |
| 毫秒(长毫秒减去) | 此方法返回此持续时间的副本，并减去以毫秒为单位的指定持续时间。 |
| 分钟(long minutestosubtract) | 此方法返回此持续时间的副本，并减去指定的持续时间(以分钟为单位)。 |
| 纳米立方体(长纳米立方体) | 此方法返回此持续时间的副本，并减去以纳秒为单位的指定持续时间。 |
| 负秒(长秒减去) | 此方法返回此持续时间的副本，并减去以秒为单位的指定持续时间。 |
| 被乘数(长被乘数) | 此方法返回此持续时间乘以标量的副本。 |
| 求反() | 此方法返回该持续时间的副本，长度为负。 |
| of(长金额，临时单位) | 此方法获取一个表示以指定单位表示的金额的持续时间。 |
| 几天(长时间) | 此方法获得一个表示标准 24 小时天数的持续时间。 |
| 小时(长时间) | 此方法获取表示标准小时数的持续时间。 |
| 毫毫秒(长毫毫秒) | 此方法获取表示毫秒数的持续时间。 |
| 分钟(长分钟) | 此方法获取表示标准分钟数的持续时间。 |
| ofnanos(长纳秒) | 此方法获取表示纳秒数的持续时间。 |
| 秒(长秒) | 此方法获取表示秒数的持续时间。 |
| 秒(长秒，长纳米调整) | 此方法获取表示秒数的持续时间和以纳秒为单位的调整。 |
| 解析(字符序列文本) | 此方法从文本字符串(如 PnDTnHnMn.nS)中获取持续时间 |
| 加号(持续时间) | 此方法返回添加了指定持续时间的该持续时间的副本。 |
| 加(long amountToAdd，temporalunit unit) | 此方法返回添加了指定持续时间的该持续时间的副本。 |
| 多天(long daysToAdd) | 此方法返回此持续时间的副本，并添加以标准 24 小时为单位的指定持续时间。 |
| 长时间添加 | 此方法返回此持续时间的副本，并添加以小时为单位的指定持续时间。 |
| 多毫秒(长毫秒) | 此方法返回此持续时间的副本，并添加以毫秒为单位的指定持续时间。 |
| 分钟数(long minutestoadd) | 此方法返回此持续时间的副本，并添加以分钟为单位的指定持续时间。 |
| 纳秒(长纳秒) | 此方法返回此持续时间的副本，并添加以纳秒为单位的指定持续时间。 |
| 多秒(长秒添加) | 此方法返回此持续时间的副本，并添加以秒为单位的指定持续时间。 |
| 减法(时间上的) | 此方法从指定的时间对象中减去此持续时间。 |
| (今日) | 此方法获取此持续时间内的天数。 |
| toHours() | 此方法获取此持续时间内的小时数。 |
| 富礼() | 此方法将此持续时间转换为总长度(毫秒)。 |
| toMinutes() | 此方法获取此持续时间内的分钟数。 |
| toNanos() | 此方法将此持续时间转换为以纳秒为单位的总长度，表示为长。 |
| toString() | 此持续时间的字符串表示形式，使用基于 ISO-8601 秒的表示形式，例如 PT8H6M12.345S |
| with 纳秒(int nanoofsecond) | 此方法以指定的纳米秒返回此持续时间的副本。 |
| 带秒(长秒) | 此方法以指定的秒数返回此持续时间的副本。 |

</figure>

**示例 1:** 这个示例说明了 Duration 类的简单使用。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing required classes
import java.time.Duration;
import java.time.LocalTime;
import java.time.temporal.ChronoUnit;

public class GFG {
   public static void main(String[] args) {

      // Initializing Duration variable
      Duration duration = Duration.between(LocalTime.NOON,LocalTime.MIDNIGHT); 

      // Printing difference between time in seconds
      System.out.println(duration.get(ChronoUnit.SECONDS));   

      // Finiding absolute difference
      Duration absDuration = duration.abs();

      // Printing absolute time difference in seconds
      System.out.println(absDuration.get(ChronoUnit.SECONDS));   
   }
}
```

**Output**

```java
-43200
43200
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing required classes
import java.time.Duration;
import java.time.temporal.ChronoUnit;

public class GFG {
   public static void main(String[] args) {

      // Getting duration in an hour
      Duration duration = Duration.from(ChronoUnit.HOURS.getDuration());

      // Printing duration in minutes
      System.out.println(duration.toMinutes());
   }
}
```

**输出:**

```java
60
```