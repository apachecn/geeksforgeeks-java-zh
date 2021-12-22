# Java 中 java.util.Date 转换为 java.time.LocalDate 的不同方式

> 原文:[https://www . geesforgeks . org/different-to-convert-Java-util-date-to-Java-time-local date-in-Java/](https://www.geeksforgeeks.org/different-ways-to-convert-java-util-date-to-java-time-localdate-in-java/)

在 Java 8 之前，为了处理时间和日期，我们有 Date、Calendar、TimeStamp (java.util)，但是有几个性能问题以及一些方法和类被弃用，所以 Java 8 引入了 java.time 包中的一些新概念 Date 和 Time API(也称为 Joda time APIs)。

**Java 7:** 日期、日历、时间戳存在于 java.util 包中。

Java 8: 时间日期 API 存在于 java.time 包中。

**将 java.util.Date 转换为 java.time.LocalDate 的不同方式:**

1.  使用实例和区域数据时间
2.  使用即时和日期。获取时间()
3.  使用 ofInstant()和 ZoneId.systemDefault()

**方法 1:使用实例和** [**区域时间**](https://www.geeksforgeeks.org/zoneddatetime-of-method-in-java-with-examples/)

**进场:**

*   首先，我们将日期对象转换为即时对象。
*   每个即时对象都与区域标识相关联，因此我们需要给出区域标识。
*   最后我们将把它转换成 LocalDate 对象。

**示例:**

*   在本程序中，我们将使用 [**到**](https://www.geeksforgeeks.org/date-toinstant-method-in-java-with-examples/) 的方法将日期对象转换为即时，该方法返回即时对象，不取参数。
*   现在我们需要使用[**【atZone()**](https://www.geeksforgeeks.org/instant-atzone-method-in-java-with-examples/)方法为其分配 zone Id 在此我们需要传递 zoneId 作为参数进行默认我们可以使用[**zoneId . system default()**。](https://www.geeksforgeeks.org/zoneid-systemdefault-method-in-java-with-examples/)
*   最后，我们将使用[**ToLocadate()**](https://www.geeksforgeeks.org/zoneddatetime-tolocaldate-method-in-java-with-examples/)方法将其转换为 LocalDate 对象。

**语法:**

```
date.toInstant().atZone(ZoneId.systemDefault()).toLocalDate()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert java.util.Date to
// java.time.LocalDate
//  Using Instance and ZonedDateTime

import java.io.*;
import java.time.*;
import java.util.Date;

class GFG {
    public static void main(String[] args)
    {

        // first create date object
        Date current = new Date();

        // first convert the date object to instant using
        // toInstant() then add zoneId using .atZone() at
        // last convert into localDate using toLocalDate()

        LocalDate local = current.toInstant()
                  .atZone(ZoneId.systemDefault())
                  .toLocalDate();

        // printing the local date object
        System.out.println(local);
    }
}
```

**Output**

```
2020-12-21
```

**方法二:使用即时和**[**date . gettime()**](https://www.geeksforgeeks.org/date-gettime-method-in-java-with-examples/)

这种方法几乎与第一种相似，唯一的区别是创建即时对象的方式。

*   这里我们就用[**instant . ofepochmilli()**T5】的方法，它以日期为论据。](https://www.geeksforgeeks.org/instant-ofepochmilli-method-in-java-with-examples/)
*   在此之后，我们将再次使用**【Atzone()】**方法添加 ZoneId，然后使用**ToLocadate()**方法获取 LocalDate 对象。

**语法:**

```
Instant.ofEpochMilli(date.getTime()) .atZone(ZoneId.systemDefault()).toLocalDate()
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert java.util.Date to
// java.time.LocalDate
// Using Instant and Date.getTime()

import java.io.*;
import java.time.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // first create date object
        Date current = new Date();

        // first create instant object using
        // Instant.ofEpochMilli(date.getTime()) than add
        // zoneId using .atZone() at last convert into
        // localDate using toLocalDate()
        LocalDate local = Instant.ofEpochMilli(current.getTime())
                  .atZone(ZoneId.systemDefault())
                  .toLocalDate();

        // printing the local date object
        System.out.println(local);
    }
}
```

**Output**

```
2020-12-21
```

**方法三:使用**[**of instant()**](https://www.geeksforgeeks.org/localtime-ofinstant-method-in-java-with-examples/)**和**[**zoneid . system default()**](https://www.geeksforgeeks.org/zoneid-systemdefault-method-in-java-with-examples/)

*   这是最简单的方法我们将使用 Java 9 的 **ofInstant()** 方法的 LocalDate 类它需要两个参数。
*   第一个参数是即时日期对象，第二个参数是区域标识。
*   在这里的第一个参数中，我们将使用 **toInstant()** 方法来获取即时对象，对于第二个参数，我们将使用**zoneid . system default()**。

**语法**

```
LocalDate.ofInstant(date.toInstant(), ZoneId.systemDefault());
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert java.util.Date to
// java.time.LocalDate
//  Using ofInstant() and ZoneId.systemDefault()

import java.io.*;
import java.time.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // first create date object
        Date current = new Date();

        // use ofInstant method of LocalDate class
        // pass instant object and zone id as parameters

        LocalDate local = LocalDate.ofInstant(
            current.toInstant(), ZoneId.systemDefault());

        // printing the local date object
        System.out.println(local);
    }
}
```

**Output**

```
2020-12-21
```