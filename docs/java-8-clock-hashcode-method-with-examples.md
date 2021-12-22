# Java 8 时钟 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-hashcode-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-hashcode-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。
Clock 类的 hashCode()方法返回这个 Clock 对象的哈希代码。Clocks 对象根据其状态重写此方法。如果时钟对象没有被覆盖，这个方法的行为由 Object.hashCode()定义。如果对象没有改变，hashcode 总是相同的。
Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用对象的唯一代码(hashcode)来搜索对象。

**语法:**

```java
public int hashCode()
```

**返回:**该方法为该时钟方法返回一个合适的哈希代码。

**示例:**

```java
Input:: 
a clock class Object e.g Clock.systemDefaultZone()

Output::
HashCode  e.g. 227139178

Explanation:: 
when hashCode() is called, then it will return a hashCode for Class Object. 
```

下面的程序说明了 java.time.Clock 类的 hashCode()方法:

**程序 1:** 用 systemDefaultZone 创建 Clock 对象，使用 Clock 对象的 hashCode()获取 hash Code 并打印。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate
// hashCode() method of Clock class

import java.time.*;

// create class
public class hashCodeMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock Object
        Clock clock = Clock.systemDefaultZone();

        // get hash Code of Clock
        // object using hashCode() method
        int code = clock.hashCode();

        // print details of TimeZone
        System.out.println("hash Code for class "
                           + clock + " is " + code);
    }
}
```

**Output:** 

```java
hash Code for class SystemClock[Etc/UTC] is 227139178
```

**程序 2:** 使用 hashCode()获取“亚洲/加尔各答”区域的时钟对象的 HashCode

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate
// hashCode() method of Clock class

import java.time.*;

// create class
public class hashCodeMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Calcutta
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

        // create Clock Object by passing zoneID
        Clock clock = Clock.system(zoneId);

        // get hash Code of Clock
        // object using hashCode() method
        int code = clock.hashCode();

        // print details of TimeZone
        System.out.println("hashCode for clock object "
                           + clock + " is " + code);
    }
}
```

**Output:** 

```java
hashCode for clock object SystemClock[Asia/Calcutta] is -681304889
```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # hashCode–](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#hashCode--)