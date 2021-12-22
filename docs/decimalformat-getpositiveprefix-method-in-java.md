# Java 中的 DecimalFormat getPositivePrefix()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-getpositiveprefix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getpositiveprefix-method-in-java/)

Java 中**十进制格式**类的 **getPositivePrefix()** 方法用于获取这个十进制格式实例的正前缀值。

**语法** :

```java
public String getPositivePrefix()

```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式实例的正前缀值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// getPositivePrefix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a positive prefix value
        deciFormat.setPositivePrefix("positive");

        // Get the positive prefix value
        String positivePrefix = deciFormat.getPositivePrefix();

        System.out.println(positivePrefix);
    }
}
```

**输出:**

```java
positive

```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/text/decimal format . html # get home prefix()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getPositivePrefix())