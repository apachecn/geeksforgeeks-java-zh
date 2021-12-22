# Java 中的 DecimalFormat getNegativeSuffix()方法

> 原文:[https://www . geesforgeks . org/decimal format-getnegatesuffix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getnegativesuffix-method-in-java/)

Java 中**十进制格式**类的 **getNegativeSuffix()** 方法用于获取这个十进制格式实例的负后缀值。

**语法** :

```java
public String getNegativeSuffix()

```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式实例的负后缀值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// getNegativeSuffix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a negative suffix
        deciFormat.setNegativeSuffix("negative");

        // Get the negative suffix value
        String negativeSuffix = deciFormat.getNegativeSuffix();

        System.out.println(negativeSuffix);
    }
}
```

**输出:**

```java
negative

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getNegativeSuffix()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getNegativeSuffix())