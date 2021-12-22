# Java 中的即时 hashCode()方法，示例

> 原文:[https://www . geesforgeks . org/instant-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-hashcode-method-in-java-with-examples/)

**瞬类**的 **hashCode()** 方法用于获取该瞬的 hashCode。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用对象的唯一代码(hashcode)来搜索对象。

**语法:**

```
public int hashCode()
```

**返回:**该方法返回本瞬间的**哈希码**。

下面的程序说明了 Instant.hashCode()方法:

**程序 1:**

```
// Java program to demonstrate
// Instant.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-12-30T19:34:50.63Z");

        // get hashCode
        // using hashCode()
        int value = instant.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + value);
    }
}
```

**输出:**

```
hashCode value: -683539878

```

**程序二:**

```
// Java program to demonstrate
// Instant.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current Instant: "
                           + instant);

        // get hashCode
        // using hashCode()
        int value = instant.hashCode();

        // print result
        System.out.println("hashCode value: "
                           + value);
    }
}
```

**输出:**

```
Current Instant: 2018-11-27T04:45:52.428Z
hashCode value: 1896457472

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#hashCode())