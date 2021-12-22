# Java 8 时钟等于()方法示例

> 原文:[https://www . geesforgeks . org/Java-8-clock-equals-method-with-examples/](https://www.geeksforgeeks.org/java-8-clock-equals-method-with-examples/)

java 时钟类是 Java 的日期时间应用编程接口的一部分。Java 日期时间应用编程接口是从 Java 版本 8 中添加的。
Java . time . Clock 类的 equals()方法检查两个 Clock 对象是否相等。如果时钟相等，则返回真，否则返回假。时钟类的这个 equals 方法重写这个 Object.equals(java.lang.Object)方法，以便根据时钟对象状态进行比较。如果没有被覆盖，那么这个 equal()方法采用 java.lang.Object.equals()的描述

**语法:**

```
public boolean equals(Object obj)
```

**参数:**该方法取一个强制参数 **obj** ，该参数是传递给与现有时钟对象进行比较的时钟对象。
**返回值:**如果两个时钟对象相等，此方法返回*真*。否则，返回*假*。

**示例:**

```
Input: 
Clock object of ZoneId "UTC"
Clock object of ZoneId "Asia/calcutta"

Output:
false

Explanation:
Both objects represent Clock object of the different zone.
Hence applying equals on them returns false.
```

下面的程序说明了 java.time.Clock 类的 equals()方法:

**程序 1:** 比较两个相似类对象时。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate equals()
// method of Clock class

import java.time.Clock;
import java.time.ZoneId;

// create class
public class EqualsMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // create clock object which represents
        // UTC Zone time using system()
        Clock clock1 = Clock.system(ZoneId.of("Etc/UTC"));

        // Print Clock1 details
        System.out.println(clock1.toString());

        // Create another class Object using
        // clock class systemDefaultZone method
        Clock clock2 = Clock.systemDefaultZone();

        // Print Clock2 details
        System.out.println(clock2.toString());

        // check whether both clock objects are equal or not
        boolean equalResponse = clock1.equals(clock2);

        // print result
        System.out.println("Both clocks are equal:"
                           + equalResponse);
    }
}
```

**Output:** 

```
SystemClock[Etc/UTC]
SystemClock[Etc/UTC]
Both clocks are equal:true
```

**程序 2:** 当两个不同的类对象进行比较时。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate equals()
// method of Clock class

import java.time.Clock;
import java.time.ZoneId;

// create class
public class EqualsMethodDemo {

    // Main method
    public static void main(String[] args)
    {

        // Create a class Object using clock
        // class systemDefaultZone method
        Clock clock1 = Clock.systemDefaultZone();

        // Print Clock1 Zone details
        System.out.println("clock1 Time Zone = "
                           + clock1.getZone());

        // Create another class Object using
        // clock class systemUTC method
        Clock clock2 = Clock.systemUTC();

        // Print Clock2 Zone details
        System.out.println("clock2 Time Zone = "
                           + clock2.getZone());

        // check whether both clock objects are equal or not
        boolean equalResponse = clock1.equals(clock2);

        // print result
        System.out.println("Both clocks are equal:"
                           + equalResponse);
    }
}
```

**Output:** 

```
clock1 Time Zone = Etc/UTC
clock2 Time Zone = Z
Both clocks are equal:false
```

**参考:**T2【https://docs . Oracle . com/javase/8/docs/API/Java/time/clock . html # equals-Java . lang . object-T4】