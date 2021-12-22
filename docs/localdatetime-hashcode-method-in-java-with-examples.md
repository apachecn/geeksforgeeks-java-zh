# Java 中的 LocalDateTime hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/local datetime-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdatetime-hashcode-method-in-java-with-examples/)

**本地日期时间类**的 **hashCode()** 方法用于返回该本地日期时间实例的哈希代码。如果对象没有改变，hashcode 总是相同的。这个方法是从 Java 的 Object 类派生的，并且以类似的方式执行。

**语法:**

```
public int hashCode()
```

**参数:**此方法不接受任何参数。

**返回:**该方法返回**整数值**，该整数值是本地日期时间实例的哈希值。

下面的程序说明了 LocalDateTime.hashCode()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// LocalDateTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2017-07-22T09:32:42");

        // get hashcode for LocalDateTime
        int hashcode = local.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + hashcode);
    }
}
```

**Output:** 

```
hashCode value: -2030906730
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// LocalDateTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDateTime Object
        LocalDateTime local
            = LocalDateTime.parse("2006-01-02T19:32:42");

        // get hashcode for LocalDateTime
        int hascode = local.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + hascode);
    }
}
```

**Output:** 

```
hashCode value: 1849330620
```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local datetime . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDateTime.html#hashCode())