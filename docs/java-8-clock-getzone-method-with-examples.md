# Java 8 Clock getZone()方法示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-getzone-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-getzone-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。
Clock 类的 getZone()方法返回用于创建 Clock 类的日期和时间的时区。每个时钟类都需要一个时区来获取当前时刻，并将该实例转换为日期或时间。所以这个方法返回用于这个过程的时区。

**语法:**

```java
public abstract ZoneId getZone()
```

**返回值:**该方法返回用于创建时钟类的**时区**。
**例:**

```java
Input:: 
a clock class Object e.g Clock.systemUTC()

Output::
TimeZone e.g. Z

Explanation:: 
when Clock.getZone() is called, then it returns a Time Zone used in Class Object
```

下面的程序说明了 java.time.Clock 类的 getZone()方法:
**程序 1:** 使用 getZone()获取用 systemDefaultZone 创建的 Clock 对象的时区

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getZone()
// method of Clock class

import java.time.*;

// create class
public class getZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock Object
        Clock clock = Clock.systemDefaultZone();

        // get TimeZone of Clock object
        // using  getZone() method
        ZoneId zoneid = clock.getZone();

        // print details of TimeZone
        System.out.println("ZoneId for class "
                           + clock + " is " + zoneid);
    }
}
```

**Output:** 

```java
ZoneId for class SystemClock[Etc/UTC] is Etc/UTC
```

**程序 2:** 使用 getZone()获取 Clock 对象的时区，区域为“亚洲/加尔各答”。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate getZone()
// method of Clock class

import java.time.*;

// create class
public class getZoneMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create a Zone Id for Calcutta
        ZoneId zoneId = ZoneId.of("Asia/Calcutta");

        // create Clock Object by passing zoneID
        Clock clock = Clock.system(zoneId);

        // get TimeZone of Clock object
        // using  getZone() method
        // and save ZoneId as zoneid variable
        ZoneId zoneid = clock.getZone();

        // print details of TimeZone
        System.out.println("ZoneId for clock is "
                           + zoneid);
    }
}
```

**Output:** 

```java
ZoneId for clock is Asia/Calcutta
```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # getZone–](https://docs.oracle.com/javase/8/docs/api/java/time/Clock.html#getZone--)