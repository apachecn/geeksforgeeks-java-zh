# java 中的 java.time.Period 类

> 原文:[https://www . geesforgeks . org/Java-时间段-java 中类/](https://www.geeksforgeeks.org/java-time-period-class-in-java/)

Java 类中的**周期**类获取以年、月、日为单位的时间量或时间量。获得的时间是 ISO-8601 日历系统中基于日期的时间量，例如“4 年、5 个月和 6 天”。一段时间内支持的单位是年、月和日。所有这三个字段始终存在，但可以设置为零。

**语法:**类声明

```
public final class Period 
extends Object 
implements ChronoPeriod, Serializable
```

以下所有方法及其执行的操作以表格形式如下:

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| addTo(时间) | 此方法将此周期添加到指定的时间对象中。 |
| between(LocalDate 启动日期包括在内，LocalDate 结束日期排除在外) | 此方法获取由两个日期之间的年数、月数和天数组成的期间。 |
| 等于(对象对象) | 此方法检查此期间是否等于另一个期间。 |
| 自(临时金额) | 此方法从时间量中获取周期的实例。 |
| 获取(临时单位) | 此方法获取请求单位的值。 |
| get 年表() | 这个方法得到这个时期的年表，就是 ISO 日历系统。 |
| getDays() | 此方法获取此期间的天数。 |
| getMonths() | 此方法获取此期间的月数。 |
| getUnits() | 此方法获取此期间支持的单位集。 |
| getYears() | 此方法获取此期间的年数。 |
| hashCode() | 此方法返回此期间的哈希代码。 |
| isNegative() | 此方法检查此期间的三个单位中是否有任何一个是负数。 |
| isZero() | 此方法检查此期间的所有三个单位是否都为零。 |
| 减(临时金额到小计) | 此方法返回减去指定期间后的该期间的副本。 |
| 天数(长天数减去) | 此方法返回减去指定天数的该期间的副本。 |
| 最小月(长月至子月) | 此方法返回减去指定月份后的该期间的副本。 |
| 负年数(长年数至小计) | 此方法返回减去指定年份后的该期间的副本。 |
| 乘以(整数标量) | 此方法返回一个新实例，该实例中的每个元素都乘以指定的标量。 |
| 求反() | 此方法返回一个新实例，该实例中的每个金额都被否定。 |
| 标准化() | 此方法返回此期间的副本，其中年和月是正常的。 |
| of(整数年，整数月，整数天) | 此方法获取一个代表年、月和日的周期。 |
| 天数(整数天) | 此方法获取一个表示天数的周期。 |
| 月数(整数个月) | 此方法获取一个表示月数的周期。 |
| 工作周(整数周) | 此方法获取一个代表周数的周期。 |
| 年数(年) | 该方法获得一个代表年数的周期。 |
| 解析(字符序列文本) | 此方法从文本字符串(如 PnYnMnD)中获取句点。 |
| amounttoadd 临时挂载) | 此方法返回添加了指定期间的该期间的副本。 |
| 多天(long daysToAdd) | 此方法返回添加了指定天数的此期间的副本。 |
| 多月(长蒙得维的亚省) | 此方法返回添加了指定月份的该期间的副本。 |
| 多年(long yearstoadd) | 此方法返回添加了指定年份的此期间的副本。 |
| 减法(时间上的) | 此方法从指定的时间对象中减去此周期。 |
| toString() | 此方法将此周期输出为字符串，如 P6Y3M1D。 |
| TotalMonths() | 此方法获取此期间的总月数。 |
| 带天数(整数天) | 此方法返回指定天数的此期间的副本。 |
| 带月份(整数个月) | 此方法返回指定月数的此期间的副本。 |
| 带年份(整数年) | 此方法返回具有指定年数的此期间的副本。 |

</figure>

让我们实现这个类的一些方法。

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate Period class
// demonstrate the methods of this class
// Methods - minus() and ofMonths()

// Importing Period class from
// java.time package
import java.time.Period;

// Main class
public class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Obtaining period representing noumer of months
        // using ofmonhs() method by
        // creating object of period class
        Period p1 = Period.ofMonths(6);

        // minus() will return a copy of this period
        // with the specified period subtracted.
        Period p2 = p1.minus(Period.ofMonths(2));

        // Print and display on the console
        System.out.println(p2);
    }
}
```

**Output**

```
P4M

```

让我们举另一个例子来讨论更多的方法，即:

**方法 1:** ofDays()此类方法用于从给定的天数中获取一个周期作为参数。

**语法:**

```
public static Period ofDays(int numberOfDays)
```

**参数:**该方法接受单个参数天数，即解析成 Period 对象的天数。

**返回:**该函数返回周期，该周期是用给定天数解析的周期对象。

**方法 2:** 这个类的 addTo()方法将这个 Period 添加到特定的时态对象中。

**语法:**

```
public Temporal addTo(Temporal temporal)
```

**参数:**要调整的时态对象不应为空。

**返回类型:**进行了调整的同类型对象。

异常:该方法引发日期时间和算术异常。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate Period class
// demonstrate the methods of this class
// Methods like ofDays() and addTo()

// Importing all classes from java.time package
import java.time.*;
import java.time.temporal.Temporal;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Getting a period representing number of days
        // using ofDays() method
        Period p = Period.ofDays(24);

        // Adding this period to the
        // temporal object i.e. temp
        Temporal temp = p.addTo(LocalDate.now());

        // Print and display on the console
        System.out.println(temp);
    }
}
```

**Output**

```
2021-03-29

```