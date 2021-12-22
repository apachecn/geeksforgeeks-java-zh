# Java 8 时钟毫秒()方法示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-millis-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-millis-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。
Clock 类的 millis()方法以毫秒为单位返回时钟的当前瞬间。毫秒是从 1970-01-01T00:00Z(世界协调时)到当前时间的测量值。此方法的工作方式与 System.currentTimeMillis()方法相同。如果创建一个对象是不可接受的，那么这个方法被用来允许在高性能用例中使用 java.time.Clock。
**语法:**

```
public long millis()
```

**返回值:**该方法以毫秒为单位返回时钟的当前瞬间。
**异常:**如果无法从时钟获得瞬间，此方法抛出 **DateTimeException** 。
**示例:** :

```
Code:
Clock clock = Clock.systemDefaultZone();
long milliSeconds=clock.millis();
System.out.println(milliSeconds);

Output:: 
1534749202051

Explanation:: 
when millis() is called, then it returns a current instant
of Class Object in milliseconds. 
```

下面的程序说明了 java.time.Clock 类的 millis()方法:
**程序 1:** 使用 millis()和用 systemDefaultZone 创建的 Clock 对象

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate millis()
// method of Clock class

import java.time.*;

// create class
public class millisMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create Clock Object
        Clock clock = Clock.systemDefaultZone();

        // get Instant Object of Clock object
        // in milliseconds using millis() method
        long milliseconds = clock.millis();

        // print details of milliseconds variable
        System.out.println("Instant for class name "
                           + clock + " in milliseconds is "
                           + milliseconds);
    }
}
```

**Output**

```
Instant for class name SystemClock[Etc/UTC] in milliseconds is 1623838188802

```