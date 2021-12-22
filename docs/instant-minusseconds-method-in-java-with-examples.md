# Java 中的瞬间负秒()方法，示例

> 原文:[https://www . geesforgeks . org/instant-mins seconds-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-minusseconds-method-in-java-with-examples/)

**即时类**的**负秒()**方法从该即时中减去指定的第二个值，并将结果作为即时对象返回。这一瞬间是不可改变的。
**语法:**

```
public Instant minusSeconds(long secondsToSubtract)
```

**参数:**该方法接受一个参数**秒减**，即秒减。
**返回:**此方法在减去秒后返回**瞬间**。

异常:该方法抛出以下异常:

*   **DateTimeException** :如果结果超过最大或最小瞬间。
*   **算术异常**:如果出现数值溢出。

下面的程序说明了负秒()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Instant.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant
            = Instant.parse("2018-10-30T09:05:55.13Z");

        // current Instant
        System.out.println("Initialize instant: "
                           + instant);

        // subtract 4300 seconds from this instant
        Instant returnedValue
            = instant.minusSeconds(4300);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**Output**

```
Initialize instant: 2018-10-30T09:05:55.130Z
Returned Instant: 2018-10-30T07:54:15.130Z

```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// Instant.minusSeconds() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a Instant object
        Instant instant = Instant.now();

        // current Instant
        System.out.println("Current instant: "
                           + instant);

        // subtract 54000 from this instant
        Instant returnedValue
            = instant.minusSeconds(54000);

        // print result
        System.out.println("Returned Instant: "
                           + returnedValue);
    }
}
```

**Output:** 

```
Current instant: 2018-11-27T06:44:04.901Z
Returned Instant: 2018-11-26T15:44:04.901Z
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # mins seconds(长)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#minusSeconds(long))