# Java 中的持续时间非小时(长)方法，示例

> 原文:[https://www . geesforgeks . org/duration-minushourslong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/duration-minushourslong-method-in-java-with-examples/)

**java.time 包**中**持续时间类**的**非固定小时(长)**方法用于获取该持续时间的不可变副本，减去指定的小时数，作为参数传递。
**语法:**

```
public Duration minusHours(long numberOfHours)
```

**参数:**该方法接受一个参数**小时数**，即需要减去的小时数。它可以是正数或负数，但不能为空。
**返回值:**该方法返回**持续时间**，该持续时间是现有持续时间的不可变副本，并减去参数小时数。
**异常:**如果出现数值溢出，该方法抛出**算术异常**。
以下示例说明 Duration.minusHours()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P2DT3H4M");

        // Get the duration subtracted
        // using minusHours() method
        System.out.println(duration1'=
                               .minusHours(2));
    }
}
```

**Output:** 

```
PT49H4M
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate minusHours() method

import java.time.Duration;

public class GFG {
    public static void main(String[] args)
    {

        // Duration 1 using parse() method
        Duration duration1
            = Duration.parse("P0DT0H4M");

        // Get the duration subtracted
        // using minusHours() method
        System.out.println(duration1
                               .minusHours(5));
    }
}
```

**Output:** 

```
PT-4H-56M
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/time/duration . html # minoshours-long-T4】