# Java 中的 DecimalFormat setNegativeSuffix()方法

> 原文:[https://www . geesforgeks . org/decimal format-set negativesuffix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setnegativesuffix-method-in-java/)

Java 中的**十进制格式**类的 **setNegativeSuffix()** 方法用于为此十进制格式实例设置负后缀值。

**语法** :

```java
public void setNegativeSuffix(String newValue)

```

**参数**:此方法使用单个参数*新值*，该新值将被设置为此十进制格式实例的负后缀。

**返回值:**此方法不返回值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// setNegativeSuffix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a negative suffix value
        deciFormat.setNegativeSuffix("negative");

        // Print a number with negative suffix
        System.out.println(deciFormat.format(-123.45));
    }
}
```

**输出:**

```java
-123.45negative

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # setNegativeSuffix(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setNegativeSuffix(java.lang.String))