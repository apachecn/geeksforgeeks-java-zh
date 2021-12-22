# Java . time . year Java 类

> 原文:[https://www.geeksforgeeks.org/java-time-year-class-in-java/](https://www.geeksforgeeks.org/java-time-year-class-in-java/)

[java.time.Year](https://www.geeksforgeeks.org/year-of-method-in-java-with-examples/) 类代表 [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) 日历系统中的一年，例如 2021 年。Year 是一个代表一年的[不可变的](https://www.geeksforgeeks.org/mutable-vs-immutable-objects-in-python/)日期时间对象。该类不存储或表示月、日、时**、**或时区。该类别所代表的年份遵循如下的概率编号系统:

> 年份 0 之前是年份-1，之后是年份 1。

**语法:**类声明

```java
public final class Year extends Object implements Temporal, TemporalAdjuster, Comparable<Year>, Serializable
```

现在，让我们讨论一下今年课程的所有方法，如下表所示。稍后，我们将单独讨论它们。

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 调整 tro() | 将指定的时间对象调整为今年。 |
| atDay（） | 创建一个本地日期，其日数等于 Year 类对象中的数字 |
| atMonth() | 将今年与一个月合并，创建一个年月 |
| 在月日() | 将今年与月份日期相结合，创建一个本地日期 |
| compareTo() | 比较两年期对象。 |
| 等于() | 检查两年期对象是否相等。 |
| 格式() | 使用指定的日期时间格式化程序格式化年份。 |
| get() | 获取指定字段今年的值。 |
| getLong() | 将指定字段的值从今年作为 long |
| 获得价值 （） | 返回年的整数值。 |
| hashCode() | 返回 year 对象的 hashcode。 |
| isafter() | 检查年份是否在年份 1 之后。 |
| isBefore() | 检查年份是否在年份 1 之前。 |
| isLeap（） | 检查该年是否为闰年。 |
| isSupported() | 检查是否支持指定的临时字段。 |
| isValidMonthDay() | 检查月日是否对今年有效 |
| 长度() | 返回一年中的天数。 |
| 减() | 返回减去指定金额后的本年副本 |
| 稳定年份() | 从一年中减去若干年，并返回一个新的 year 对象。 |
| 现在() | 获取当前年份并创建一个 year 对象。 |
| of() | "创建年等于数字的年对象。0 用于公元 0 年，而-1 用于公元前 1 年。" |
| 解析() | 从文本字符串(如 2021)中获取年份的实例。 |
| 加号() | 返回今年的副本，并添加指定的年数。 |
| plusYears() | 将年数添加到一年中，并返回一个新的 year 对象。 |
| 查询() | 今年使用指定查询的查询。 |
| 范围() | 获取指定字段的有效值范围。 |
| toString() | 以字符串形式返回当前年份。 |
| 直到() | 根据指定的单位计算到下一年的时间。 |
| 带() | 返回年度的调整副本。 |

</figure>

让我们详细讨论一下这个类的一些常用方法，以便更好地理解，从而实现其余的方法。在这里，我们将讨论主要的方法，即:

1.  [*【atday()*](https://www.geeksforgeeks.org/year-atday-method-in-java/)
2.  *hashCode()*
3.  *[*Isafter()*](https://www.geeksforgeeks.org/year-isafter-method-in-java-with-examples/)*
4.  *[*【isefore()*](https://www.geeksforgeeks.org/year-isbefore-method-in-java-with-examples/)*
5.  *[*【iseap()*](https://www.geeksforgeeks.org/year-isleap-method-in-java-with-examples/)*
6.  *[*现在()*](https://www.geeksforgeeks.org/year-now-method-in-java-with-examples/)*
7.  *[*-()*](https://www.geeksforgeeks.org/year-minuslongunit-method-in-java-with-examples/)*

***方法 1:**[Java 中的 atDay()](https://www.geeksforgeeks.org/year-atday-method-in-java/)Year 类的方法将当前年份与作为参数传递给它的一年中的某一天结合起来，创建一个 LocalDate。*

***语法**:*

```java
*public LocalDate atDay(int dayOfYear)*
```

***参数**:该方法接受一年中的单个参数日。这是一年中的一天。它可以取 1 到 365-366 之间的值。*

***返回值**:返回一个由当年和当年的日期组成的本地日期作为参数传递给函数。*

***异常**:此方法抛出 [DateTimeException](https://www.geeksforgeeks.org/zoneoffset-ofstring-method-in-java-with-examples/) ，如果参数中传递的年月日无效，即小于等于零、大于等于 366 且当前年份不是闰年。*

***方法二:** hashCode()*

*它以整数形式返回哈希值。Hashcode 值主要用于散列基于**–**的集合，如 HashMap、HashSet、HashTable 等。该方法必须在每个覆盖[等于()方法](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)的类中被覆盖。
**语法:***

```java
*public int hashCode()

// This method returns the hash code value 
// for the object on which this method is invoked.*
```

***方法 3:***

*Java 中 Year 类的[isaafter()](https://www.geeksforgeeks.org/year-isafter-method-in-java-with-examples/)方法用于检查当前 Year 对象是否在作为该方法参数指定的 Year 之后。*

***语法**:*

```java
*public boolean isAfter(Year otherYear)*
```

***参数**:接受单个参数与当前年份对象进行比较的另一年。*

***返回值**:如果这个 Year 对象的值在指定为方法参数的 Year 对象的值之后，则返回布尔值 True，否则返回 False。*

***方法 4:***

*Java 中 Year 类的 [isBefore()](https://www.geeksforgeeks.org/year-isbefore-method-in-java-with-examples/) 方法用于检查当前 Year 对象是否在该方法参数指定的 Year 之前。*

***语法**:*

```java
*public boolean isBefore(Year otherYear)*
```

***参数**:接受单个参数 otherYear，与当前 Year 对象进行比较。*

***返回值**:如果这个 Year 对象的值在指定为方法参数的 Year 对象的值之前，则返回布尔值 True，否则返回 False。*

***方法 5:***

*Java 中的 Year 类的[isLeap()](https://www.geeksforgeeks.org/year-isleap-method-in-java-with-examples/) 方法用于根据 proleptic calendar 系统规则检查这个 Year 对象是否是闰年。*

> *如果一年有 366 天，它就是闰年。根据序言日历系统规则，一年是闰年，如果:*
> 
> *   *如果它能被 4 整除。*
> *   *它不能被 100 整除，但可以被 400 整除。*

***语法**:*

```java
*public boolean isLeap()*
```

***参数**:此方法不接受任何参数。*

***返回值**:如果这个 Year 对象的值是一个闰年，根据 proleptic 日历系统规则，它返回一个布尔值 True，否则返回 False。*

***方法 6:***

*Java 中 Year 类的[now()](https://www.geeksforgeeks.org/year-now-method-in-java-with-examples/) 方法用于从默认时区的系统时钟返回当前年份。*

***语法**:*

```java
*public static Year now()

or,
public static Year now(Clock clock)

or,
public static Year now(ZoneId zone)*
```

***参数**:该方法的参数是可选的，如上语法所示。*

***返回值**:如果没有指定参数，则从默认时区的系统时钟返回当前年份，否则使用指定的时钟和时区返回当前年份。它永远不能返回空值*

***方法 7:***

*year 类的[减()方法](https://www.geeksforgeeks.org/year-minuslongunit-method-in-java-with-examples/)用于从 Year 对象中减去指定数量的单位后返回一份今年的副本。如果不能从年份中减去指定的单位，将引发异常。此实例是不可变的，不受此方法调用的影响。*

***语法:***

```java
*public Year minus(long amountToSubtract, TemporalUnit unit)*
```

***参数:**该方法接受以下两个参数:*

*   *amountToSubtract

    *   此参数表示要从结果中减去的单位量。* 
*   *单位

    *   此参数表示要减去的量的单位。* 

***返回值:**此方法返回一个基于本年度减去指定金额的年份。*

***异常:**该方法抛出以下异常:*

*   *日期时间异常

    *   如果无法进行减法运算，则会引发此异常。* 
*   *unsupportedtemporaltypexception

    *   如果不支持该单元，将引发此异常。* 
*   *算术异常

    *   如果发生数值溢出，将引发此异常。* 

*对于 plus()方法，您可以将相同的内容关联起来。现在我们已经讨论完了方法。现在是时候实现同样的方法来演示 Year 类了。*

***实施:***

***例***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to illustrate java.time.Year class
import java.time.*;

// Importing all classes from
// time package to get other functionalities
import java.time.Year;

//  Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Object 1
        // Creating an Year class object

        // getting the current year each
        // using the now() method
        Year y = Year.now();

        // Print and display the current year
        System.out.println("Current year: " + y);

        // Object 2
        // Creating another Year class object Object
        // Here year 2020 as passed as an argument
        Year y1 = Year.of(2020);

        // Object 3
        // Creating another object of year class
        // again passing year 2022 as an argument
        Year y2 = Year.of(2022);

        // Now, creating a LocalDate object and
        // getting the local date at the day
        // passed as an argument
        // Custom input argument = 350
        LocalDate l = y.atDay(350);

        // Print the local date
        System.out.println("Local date: " + l);

        // Now, creating a YearMonth
        // and retrieving month using atMonth() method
        // by passing argument to the method
        // Custom input argument- 6
        YearMonth ym = y.atMonth(6);

        // Print the year and the month
        System.out.println("Year and month: " + ym);

        // Printing number of days of current Year
        System.out.println("Number of days: " + y.length());

        // Checking if Year y
        // is before Year y2
        System.out.println("2021 is before 2022: "
                           + y.isBefore(y2));
        // check if Year y
        // is after Year y1
        System.out.println("2021 is after 2020: "
                           + y.isAfter(y1));

        // Now, printing hashcode of the year
        // using the hashcode() method
        System.out.println("Hashcode of the year: "
                           + y.hashCode());

        // Checking whether the year is leap year or not
        System.out.println("2020 is leap year: "
                           + y1.isLeap());

        // Adding 150 years to the current year
        System.out.println("2021 - 155 years: "
                           + y.minusYears(155));
        // Subtracting 150 years from the current year
        System.out.println("2021 + 145 years: "
                           + y.plusYears(145));
    }
}*
```

***Output**

```java
Current year: 2021
Local date: 2021-12-16
Year and month: 2021-06
Number of days: 365
2021 is before 2022: true
2021 is after 2020: true
Hashcode of the year: 2021
2020 is leap year: true
2021 - 155 years: 1866
2021 + 145 years: 2166
```*