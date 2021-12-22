# java 中的 Java . nio . file . attribute . file time 类

> 原文:[https://www . geesforgeks . org/Java-nio-file-attribute-file time-class-in-Java/](https://www.geeksforgeeks.org/java-nio-file-attribute-filetime-class-in-java/)

Java . nio . file . attribute . filetime 类用于获取表示该文件时间戳的值，即该文件上次被修改、访问或创建的时间。

**类别申报:**

```
public final class FileTime
extends Object
implements Comparable<FileTime>
```

**方法:**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| 比较(文件时间其他) | 此方法比较订单的两个文件时间对象的值。 |
| 等于(对象对象) | 此方法测试此文件时间是否与给定对象相等。 |
| 从(即时即时) | 此方法返回一个文件时间，表示与提供的即时对象在时间线上相同的时间点值。 |
| 从(长值，时间单位单位) | 此方法返回一个表示给定粒度单位的值的文件时间。 |
| 从毫秒(长值) | 此方法返回一个表示给定值的文件时间(以毫秒为单位)。 |
| hashCode() | 此方法计算此文件时间的哈希代码。 |
| 至(时间单位单位) | 此方法返回给定粒度单位的值。 |
| t 常量() | 此方法将此文件时间对象转换为即时。 |
| 富礼() | 此方法以毫秒为单位返回值。 |
| toString() | 此方法返回此文件时间的字符串表示形式。 |

</figure>

下面是 java 中 Java . nio . file . attribute . filetime 类的一些方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.nio.file.attribute.FileTime;
import java.time.Instant;
import java.util.concurrent.TimeUnit;

public class GFG {
    public static void main(String[] args)
    {
        // Variables for storing time values
        long v1 = 21;
        long v2 = 356;

        // Creating an Instant.
        Instant instant
            = Instant.parse("2017-02-03T10:37:30.00Z");

        // Creating FileTime object using from
        // Method This method takes an Integer
        // value and a timeunit as parameters.
        FileTime filetime2
            = FileTime.from(v2, TimeUnit.MILLISECONDS);

        // Creating FileTime object using fromMillis method.
        FileTime filetime1 = FileTime.fromMillis(v1);

        // Creating FileTime object using from Method
        // This method takes an Instant as parameters.
        FileTime filetime3 = FileTime.from(instant);

        // Method to convert this filetime to an instant.
        Instant instantFromFileTime = filetime3.toInstant();

        // Method to convert filetime1 to this timeunit.
        System.out.println(
            filetime1.to(TimeUnit.MILLISECONDS));

        // Method to check if filetime1
        // is equal to filetime2 or not.
        if (filetime1.equals(filetime2))
            System.out.println("FileTime are equal");
        else
            System.out.println("FileTime are not equal");

        // Method to print hashvalue of filetime1.
        System.out.println(filetime1.hashCode());

        // Method to convert filetime1 to milliseconds.
        System.out.println(filetime1.toMillis());

        // Method to comapre filetime1 and filetime2.
        System.out.println(filetime1.compareTo(filetime2));

        // Method to print string
        // representation of filetime1.
        System.out.println(filetime1.toString());
    }
}
```

**Output**

```
21
FileTime are not equal
1071000000
21
-1
1970-01-01T00:00:00.021Z
```