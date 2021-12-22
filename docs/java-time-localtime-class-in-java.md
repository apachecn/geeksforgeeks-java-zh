# java 中的 java.time.LocalTime 类

> 原文:[https://www . geesforgeks . org/Java-time-local time-in-Java 类/](https://www.geeksforgeeks.org/java-time-localtime-class-in-java/)

Java 是最流行的编程语言，也是应用最广泛的编程语言。Java 用于各种应用，如移动应用、桌面应用、网络应用。像在 Java 中一样，java.time.LocalTime 类表示时间，时间被视为小时-分-秒。这个类是不可变的，也是线程安全的。java.time.LocalTime 类下有各种各样的方法，这将在下面解释，实现也将在下面执行。 ***java.time*** 是一个用来处理当前日期和时间 API 的包。

*   导入 java.time.LocalTime 等类。
*   现在使用 LocalTime.now()存储当前时间。
*   显示存储在变量中的当前时间。

首先，这个类的大多数方法都以表格的形式展示如下:

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 调整(暂时的) | 所有方法静态方法实例方法具体方法修改量和类型方法和说明

暂时的 |
| Date(本地日期日期) | 将此时间与日期相结合，创建一个本地日期时间。 |
| 区域位移(ZoneOffset) | 将此时间与偏移量相结合，创建一个偏移量。 |
| 比较(本地时间其他) | 将这次与另一次进行比较。 |
| 等于(对象对象) | 检查这个时间是否等于另一个时间。 |
| 格式(日期格式器格式器) | 使用指定的格式化程序格式化这次。 |
| get(临时字段) | 以 int 形式获取指定字段的值。 |
| getHour() | 获取一天中的小时字段。 |
| getMinute() | 获取分钟字段。 |
| getNano() | 获取纳米秒字段。 |
| getSecond() | 获取分钟秒字段。 |
| hashCode() | 这次的哈希代码。 |
| isAfter(本地时间其他) | 检查该时间是否在指定时间之后。 |
| isBefore(LocalTime 其他) | 检查该时间是否在指定时间之前。 |
| 问题支持(临时字段) | 检查指定的字段是否受支持。 |
| 减(长量到子体积，时间单位) | 返回减去指定数量后的时间副本。 |
| 小时(长小时减去) | 返回减去指定小时数后的本地时间副本。 |
| 分钟(long minutestosubtract) | 返回减去指定分钟数后的本地时间副本。 |
| 纳米立方体(长纳米立方体) | 返回减去指定纳秒数后的本地时间副本。 |
| 负秒(长秒减去) | 返回减去指定秒数后的本地时间副本。 |
| 现在() | 从默认时区的系统时钟获取当前时间。 |
| of(整数小时，整数分钟) | 从小时和分钟获取 LocalTime 的实例。 |
| 无纳米虫(长纳米虫) | 从纳米日值中获取 LocalTime 的实例。 |
| of ofsecondofday(long second fday) | 从一天中的第二个值获取 LocalTime 的实例。 |
| 解析(字符序列文本) | 从文本字符串(如 10:15)中获取 LocalTime 的实例。 |
| amounttoadd 临时挂载) | 返回添加了指定数量的时间副本。 |
| 长时间添加 | 返回添加了指定小时数的本地时间的副本。 |
| 分钟数(long minutestoadd) | 返回添加了指定分钟数的本地时间的副本。 |
| 纳秒(长纳秒) | 返回添加了指定纳秒数的本地时间的副本。 |
| 多秒(长秒添加) | 返回添加了指定秒数的本地时间的副本。 |
| 查询(临时查询<r>查询)</r> | 这次使用指定的查询进行查询。 |
| 范围(临时字段) | 获取指定字段的有效值范围。 |
| toNanoOfDay() | 以纳米为单位提取时间，从 0 到 24 * 60 * 60 * 1，000，000，000–1。 |
| 截断至(时间单位) | 返回时间被截断的本地时间的副本。 |
| 带(临时调节器) | 返回此时间的调整副本。 |
| 小时数 | 返回更改了一天中某个小时的本地时间的副本。 |
| 带分钟(整数分钟) | 返回该本地时间的副本，并更改分钟。 |
| withnano(int nanofsecond) | 返回该本地时间的副本，更改后的时间为纳米秒。 |
| 带秒(整数秒) | 返回该本地时间的副本，更改分钟的秒数。 |

</figure>

**实施:**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate LocalTime Class

// Importing LocalDateTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class  GFG {

    // Main driver method
    public static void main(String args[]) {

      // Creating an object of LocalTime class by
      // declaring a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

      // Print and display the LocalTime value
        System.out.println("Local time value : "+ltime);       
    }
}
```

**Output**

```java
Local time value : 06:20:52.986897
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

    // main driver method
    public static void main(String args[])
    {
        // Creating an object of LocalTime Class by
        // declaring a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

      // Now plusMinute() will add up minutes to the LocalTime
        LocalTime time3 = ltime.plusMinutes(120);

        // Display the time using object of class
        System.out.println("Time : "+time3);
    }
}
```

**Output**

```java
Time : 08:34:59.135137
```

**例 3**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

   // Main class
    public static void main(String args[])
    {
        // Creating an object of LocalTime class by
        // declare a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

        // plusHours() method will add up Hours to
        // the LocalTime
        LocalTime time3 = ltime.plusHours(05);

        // Display the time
        System.out.println(time3);
    }
}
```

**Output**

```java
17:48:53.003478
```

**例 4**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate LocalTime
// where plusMethod() is illustrated

// Importing LocalTime class from
// java.time package
import java.time.LocalTime;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // creating an object of. LocalTime Class by
        // declare a variable to store LocalTime
        LocalTime ltime = LocalTime.now();

        // minusMinute() will subtract minutes from
        // the LocalTime
        LocalTime time = ltime.minusMinutes(120);

        // Display the time
        System.out.println(time);
    }
}
```

**Output**

```java
10:54:49.649675
```