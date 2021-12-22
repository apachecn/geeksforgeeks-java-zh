# Java 中的计时单位值()方法，示例

> 原文:[https://www . geeksforgeeks . org/chronounit-value of-method-in-Java-with-examples/](https://www.geeksforgeeks.org/chronounit-valueof-method-in-java-with-examples/)

**计时单位枚举**的 **valueOf()** 方法用于以指定的名称返回该类型的枚举单位。

**语法:**

```java
public static ChronoUnit valueOf(String name)

```

**参数:**该方法接受**名称**，这是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的**枚举常量**。

**异常:**
这个方法抛出如下异常:

*   **IllegalArgumentException** :如果这个枚举类型没有指定名称的常量。
*   **NullPointRexception**:如果参数为空。

以下程序说明了计时单位.值()方法:
**程序 1:**

```java
// Java program to demonstrate
// ChronoUnit.valueOf() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("MILLENNIA");

        // print
        System.out.println("ChronoUnit: "
                           + chronoUnit);
    }
}
```

**Output:**

```java
ChronoUnit: Millennia

```

**程序 2:**

```java
// Java program to demonstrate
// ChronoUnit.valueOf() method

import java.time.temporal.ChronoUnit;

public class GFG {
    public static void main(String[] args)
    {

        // get ChronoUnit
        ChronoUnit chronoUnit
            = ChronoUnit.valueOf("CENTURIES");

        // print
        System.out.println("ChronoUnit: "
                           + chronoUnit);
    }
}
```

**Output:**

```java
ChronoUnit: Centuries

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/temporal/chronounit . html # value of(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/java/time/temporal/ChronoUnit.html#valueOf(java.lang.String))