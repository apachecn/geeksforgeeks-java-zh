# Java 中 FormatStyle valueOf()方法，示例

> 原文:[https://www . geesforgeks . org/format style-value of-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatstyle-valueof-method-in-java-with-examples/)

**FormatStyle 枚举**的 **valueOf()** 方法用于获取具有指定名称的该类型 FormatStyle 的枚举值。

**语法:**

```java
public static FormatStyle valueOf(String name)

```

**参数:**该方法接受一个**名称**作为参数，该参数是要返回的枚举常量的名称。

**返回值:**该方法返回指定名称的**枚举常量**。

**异常:**该方法抛出以下异常:

*   **IllegalArgumentException** :如果这个枚举类型没有指定名称的常量。
*   **NullPointRexception**:如果参数为空。

下面的程序说明了 FormatStyle.valueOf()方法:
**程序 1:**

```java
// Java program to demonstrate
// FormatStyle.valueOf() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("LONG");

        // Print the result
        System.out.println("FormatStyle: "
                           + formatStyle);
    }
}
```

**Output:**

```java
FormatStyle: LONG

```

**程序 2:**

```java
// Java program to demonstrate
// FormatStyle.valueOf() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("FULL");

        // Print the result
        System.out.println("FormatStyle: "
                           + formatStyle);
    }
}
```

**Output:**

```java
FormatStyle: FULL

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/format style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/FormatStyle.html)