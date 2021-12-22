# Java 中的 ChronoField checkValidValue()方法，示例

> 原文:[https://www . geesforgeks . org/chronofield-checkvalidvalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronofield-checkvalidvalue-method-in-java-with-examples/)

**计时场枚举**的**检查有效值()**方法用于检查作为参数传递的值对于计时场常数是否有效。

**语法:**

```java
public long checkValidValue(long value)

```

**参数:**该方法接受**值**，该值是要检查的值。

**返回值:**这个方法返回传入的值。

下面的程序说明了时间域检查有效值()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoField.checkValidValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("MINUTE_OF_DAY");

        // apply checkValidValue()
        long validInt
            = chronoField.checkValidValue(360);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**Output:**

```java
Value passed :360

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoField.checkValidValue() method

import java.time.temporal.ChronoField;

public class GFG {
    public static void main(String[] args)
    {

        // get chronoField
        ChronoField chronoField
            = ChronoField.valueOf("DAY_OF_WEEK");

        // apply checkValidValue()
        long validInt
            = chronoField.checkValidValue(2);

        // print
        System.out.println("Value passed :"
                           + validInt);
    }
}
```

**Output:**

```java
Value passed :2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronofield . html # checkValidValue(长)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoField.html#checkValidValue(long))