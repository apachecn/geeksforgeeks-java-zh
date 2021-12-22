# Java 中的即时解析()方法，示例

> 原文:[https://www . geesforgeks . org/instant-parse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-parse-method-in-java-with-examples/)

**Instant 类**的 **parse()** 方法有助于从作为参数传递的字符串值中获取 Instant 的实例。该字符串是世界协调时时区中的一个瞬间。它是使用 DateTimeFormatter 解析的。ISO_INSTANT。

**语法:**

```
public static Instant 
    parse(CharSequence text)
```

**参数:**该方法接受一个参数**文本**，即即时要解析的文本。它不应为空。

**返回:**该方法返回一个**时刻**，这是作为参数传递的字符串在世界协调时的有效时刻。

**异常:**如果文本无法解析，这个方法抛出 **DateTimeException** 。

下面的程序说明了 parse()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // get Instant using parse method
        Instant instant
            = Instant.parse("2018-11-30T18:35:24.00Z");

        // print result
        System.out.println("Instant: "
                           + instant);
    }
}
```

**输出:**

```
Instant: 2018-11-30T18:35:24Z

```

**程序二:**

```
// Java program to demonstrate
// Instant.parse() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // get Instant using parse method
        Instant instant
            = Instant.parse("2019-10-01T08:25:24.00Z");

        // print result
        System.out.println("Instant: "
                           + instant);
    }
}
```

**输出:**

```
Instant: 2019-10-01T08:25:24Z

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # parse(Java . lang . charsequence)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#parse(java.lang.CharSequence))