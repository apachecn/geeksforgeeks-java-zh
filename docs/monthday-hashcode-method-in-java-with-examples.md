# Java 中的 MonthDay hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/month day-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/monthday-hashcode-method-in-java-with-examples/)

**hashCode()**月日**类的**方法用于获取这个月日的 hashCode。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希相关算法进行一些操作，比如哈希表、哈希表等。也可以用对象的唯一代码(hashcode)来搜索对象。

**语法:**

```java
public int hashCode()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回一个合适的哈希码。

下面的程序说明了 hashCode()方法:
**程序 1:**

```java
// Java program to demonstrate
// MonthDay.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--10-12");

        // print hashcode
        System.out.println("hashCode"
                           + " of YearMonth: "
                           + month.hashCode());
    }
}
```

**Output:**

```java
hashCode of YearMonth: 652

```

**程序 2:**

```java
// Java program to demonstrate
// MonthDay.from() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a MonthDay object
        MonthDay month = MonthDay.parse("--08-31");

        // print hashcode
        System.out.println("hashCode"
                           + " of YearMonth: "
                           + month.hashCode());
    }
}
```

**Output:**

```java
hashCode of YearMonth: 543

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/monthday . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/MonthDay.html#hashCode())