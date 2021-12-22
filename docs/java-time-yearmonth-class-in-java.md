# java 中的 Java . time . year . month 类

> 原文:[https://www . geesforgeks . org/Java-time-year-month-in-Java 类/](https://www.geeksforgeeks.org/java-time-yearmonth-class-in-java/)

Java **YearMonth 类**提供“年-月”格式的输出。这个类是一个不可变的类，这意味着它定义的对象一旦被创建，就不会改变它们的值。从一年和一个月中导出的任何字段，如一年的季度，通常都可以获得。此类不存储或表示日期、时间或时区。例如，它不会显示值“11 月-2006-12:00”，而会显示“2007-11”。它继承了 thing 类并实现了 Comparable 接口。

Java YearMonth 类实现时态，临时调整，可比较<yearmonth>，可序列化</yearmonth>

> 公共最终类 YearMonth 扩展对象
> 
> 实现时态，时态调整，可比较<yearmonth>，可序列化</yearmonth>

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| 调整(暂时的) | 此方法将指定的时态对象调整为今年的月份。 |
| atDay（int dayOfMonth） | 这个方法将年-月和月-日结合起来创建一个本地日期。 |
| atEndOfMonth() | 此方法返回月末的本地日期。 |
| 比较(年月其他) | 这种方法将今年的月份与另一年的月份进行比较。 |
| 等于(对象对象) | 这个方法检查这个年-月是否等于另一个年-月。 |
| 格式(日期格式器格式器) | 此方法使用指定的格式化程序格式化今年的月份。 |
| 来自(临时过程或临时) | 此方法从时态对象中获取 YearMonth 的实例。 |
| get(临时字段) | 此方法以 int 形式获取指定字段今年-月的值。 |
| getLong(临时字段) | 此方法从今年-月开始获取指定字段的值。 |
| getMonth（） | 此方法使用月份枚举获取年度月份字段。 |
| getMonthValue() | 此方法获取从 1 到 12 的年月字段。 |
| getYear（） | 此方法获取年份字段。 |
| hashCode() | 今年这个月的哈希代码。 |
| 一年后(另一个月) | 此方法检查该年-月是否在指定的年-月之后。 |
| 一年前(其他月份) | 此方法检查该年-月是否在指定的年-月之前。 |
| isleapyear() | 根据国际标准化组织日历系统规则，此方法检查年份是否为闰年。 |
| 问题支持(临时字段) | 此方法检查指定的字段是否受支持。 |
| 发行支持(临时单位) | 此方法检查指定的单元是否受支持。 |
| isValidDay（int dayOfMonth） | 此方法检查月日是否对此年月有效。 |
| 月长度() | 此方法返回月的长度，同时考虑年。 |
| 一年的长度() | 此方法返回一年的长度。 |
| 减(长量到子体积，时间单位) | 此方法返回减去指定金额后的本年度-月份的副本。 |
| 减(临时金额到小计) | 此方法返回减去指定金额后的本年度-月份的副本。 |
| 最小月(长月至子月) | 此方法返回减去指定月数后的本年度月的副本。 |
| 负年数(长年数至小计) | 此方法返回减去指定年数的本年度月的副本。 |
| 现在() | 此方法从默认时区的系统时钟中获取当前的年-月。 |
| 现在(时钟) | 此方法从指定的时钟获取当前的年-月。 |
| 现在(区域标识区域) | 此方法从指定时区的系统时钟中获取当前的年-月。 |
| of(整年整月) | 此方法从年和月中获取 YearMonth 的实例。 |
| 年月日 | 此方法从年和月中获取 YearMonth 的实例。 |
| 解析(字符序列文本) | 此方法从文本字符串(如 2007-12)中获取 YearMonth 的实例。 |
| 解析(字符序列文本，日期时间格式化程序格式化程序) | 此方法使用特定的格式化程序从文本字符串中获取 YearMonth 的实例。 |
| 加(long amountToAdd，temporalunit unit) | 此方法返回添加了指定金额的本年度-月份的副本。 |
| amounttoadd 临时挂载) | 此方法返回添加了指定金额的本年度-月份的副本。 |
| 多月(长蒙得维的亚省) | 此方法返回添加了指定月数的本年度月的副本。 |
| 多年(long yearstoadd) | 此方法返回添加了指定年数的本年度月的副本。 |
| 查询(临时查询<r>查询)</r> | 此方法使用指定的查询来查询本年度-月份。 |
| 范围(临时字段) | 此方法获取指定字段的有效值范围。 |
| toString() | 此方法以字符串形式输出今年-月，如 2007-12。 |
| 直到(临时结束，临时单位) | 此方法根据指定的单位计算到下一年的时间。 |
| 带(临时调节器) | 此方法返回今年-月的调整副本。 |
| 带(临时字段，长新值) | 此方法返回指定字段设置为新值的本年度-月份的副本。 |
| 带月(整数月) | 这个方法返回一份今年月的副本，其中修改了年月。 |
| 带年份(整年) | 这个方法返回一个年月的副本，并更改年份。 |

</figure>

下面是 Java YearMonth 类的一些方法的实现:

**1。plus():** 返回添加了所需金额的本年度-月份的副本。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// plus() Method implementation
import java.time.*;
public class Example {
    public static void main(String[] args)
    {
        YearMonth obj1 = YearMonth.now();

        // plus(Period.ofYears(int)) will add
        // no.of years to the existing year
        YearMonth obj2 = obj1.plus(Period.ofYears(0));
        System.out.println(obj2);
    }
}
```

**Output**

```
2021-02
```

**2。减():**返回减去所需金额后的本年度-月份的副本。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// minus() method implementation
import java.time.*;
public class Example {
    public static void main(String[] args)
    {
        YearMonth obj1 = YearMonth.now();

        //.minus(Period.ofYears(int)) will subtract
        // no. ofyears from the existing year
        YearMonth obj2 = obj1.minus(Period.ofYears(3));
        System.out.println(obj2);
    }
}
```

**Output**

```
2018-02
```