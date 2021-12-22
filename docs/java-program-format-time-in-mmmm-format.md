# MMMM 格式的 Java 程序格式时间

> 原文:[https://www . geesforgeks . org/Java-program-format-time-in-mmmm-format/](https://www.geeksforgeeks.org/java-program-format-time-in-mmmm-format/)

在 Java 中，月份的 MMM 格式是月份的简短形式，使用 3 个字符。 ***SimpleDateFormat 类*** 用于在 java 中实现这种格式，您可以使用以下代码导入这个包。

```
import java.text.SimpleDateFormat

```

**示例:**

<figure class="table">

| 月份名称(MMMM 格式) | MMM 格式 |
| --- | --- |
| 一月 | 一月 |
| 二月 | 二月（February 的缩写） |
| 三月 | 瑕疵 |
| 四月 | 四月 |
| 五月 | 五月 |
| 六月 | 六月 |
| 七月 | 七月 |
| 八月 | 八月 |
| 九月 | 九月 |
| 十月 | 十月 |
| 十一月 | 十一月 |
| 十二月 | 十二月 |

</figure>

**MMMM 格式:**

月份的 MMMM 格式是月份的全称。例如，1 月、2 月、3 月、4 月、5 月等是当月的 MMMM 格式。

在这里，您将看到完整的包，说明如何使用简单日期格式类来扩展日期格式类。SimpleDateFormat 类也有助于将日期转换为文本格式，并且它还可以将文本解析为日期格式并进行规范化。

```
Class SimpleDateFormat
     java.lang.Object
        java.text.Format
            java.text.DateFormat
                 java.text.SimpleDateFormat

```

**示例 1:** 以 MMM 和 MMMM 格式显示月份

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to display Month 
// in MMM and MMMM Format
import java.text.SimpleDateFormat;
import java.util.Date;

public class GFG {

public static void main(String[] argv) throws Exception {

    // Setting the date object
    Date dat = new Date();
    SimpleDateFormat dateFormat;

    // Setting MMM Format
    dateFormat = new SimpleDateFormat("MMM");
    System.out.println(dateFormat.format(dat));

    // Setting MMMM Format
    dateFormat = new SimpleDateFormat("MMMM");
    System.out.println(dateFormat.format(dat));
}
}
```

**输出:**

```
Nov
November

```

**示例 2:** 以 MMMM 格式显示日期和时间

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Display Date
// and Time in MMMM Format
import java.text.SimpleDateFormat;
import java.util.Date;

public class GFG {

public static void main(String[] argv) throws Exception {

    // Setting the date object
    Date dat = new Date();
    SimpleDateFormat dateFormat;

    // Setting the date and time in MMMM format
    dateFormat = new SimpleDateFormat("EEEE  dd MMMM yyyy kk:mm:ss");
    System.out.println(dateFormat.format(dat));
}
}
```

**输出:**

```
Monday  02 November 2020 11:46:05

```