# Java 中的 decimal format setpositionvesuffix()方法

> 原文:[https://www . geesforgeks . org/decimal format-set positivesuffix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setpositivesuffix-method-in-java/)

Java 中**十进制格式**类的**setpositionvesuffix()**方法用于为此十进制格式实例设置一个正后缀值。

**语法** :

```java
public void setPositiveSuffix(String newValue)

```

**参数**:此方法使用单个参数*新值*，该新值将被设置为此十进制格式实例的正后缀。

**返回值:**此方法不返回值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// setPositiveSuffix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a positive suffix value
        deciFormat.setPositiveSuffix("positive");

        // Print a number with positive suffix
        System.out.println(deciFormat.format(12345));
    }
}
```

**输出:**

```java
12, 345positive

```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/text/decimal format . html # set context suffix(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setPositiveSuffix(java.lang.String))