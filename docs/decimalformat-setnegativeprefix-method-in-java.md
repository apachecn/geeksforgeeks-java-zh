# Java 中的 DecimalFormat setNegativePrefix()方法

> 原文:[https://www . geesforgeks . org/decimal format-set negativeprefix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setnegativeprefix-method-in-java/)

Java 中的**十进制格式**类的 **setNegativePrefix()** 方法用于设置这个十进制格式实例的负值。

**语法** :

```java
public void setNegativePrefix(String newValue)

```

**参数**:这个方法有一个单一的参数 newValue，它是这个十进制格式实例的一个负前缀。

**返回值:**此方法不返回值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// setNegativePrefix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a negative prefix value
        deciFormat.setNegativePrefix("negative");

        // Print a number with negative prefix set
        System.out.println(deciFormat.format(-123.45));
    }
}
```

**输出:**

```java
negative123.45

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setnevableprefix(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setNegativePrefix(java.lang.String))