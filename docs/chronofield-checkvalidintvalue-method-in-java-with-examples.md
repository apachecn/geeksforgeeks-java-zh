# Java 中的 ChronoField checkValidIntValue()方法，示例

> 原文:[https://www . geesforgeks . org/chronofield-checkvalidintvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-checkvalidintvalue-method-in-java-with-examples/)

**时域枚举**的 **checkValidIntValue()** 方法用于检查作为参数传递的值对于时域常量是否有效，值是否符合整数。

**语法:**

```java
public int checkValidIntValue(long value)

```

**参数:**该方法接受**值**，该值是要检查的值。

**返回值:**这个方法返回传入的值。

下面的程序说明了计时场. checkValidIntValue()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoField.checkValidIntValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("HOUR_OF_DAY");

        // apply checkValidIntValue()
        int validInt
            = chronoField.checkValidIntValue(21);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**Output:**

```java
Value passed :21

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoField.checkValidIntValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("YEAR_OF_ERA");

        // apply checkValidIntValue()
        int validInt
            = chronoField.checkValidIntValue(2021);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**Output:**

```java
Value passed :2021

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # checkValidIntValue(长)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#checkValidIntValue(long))