# Java 中的 DecimalFormat getNegativePrefix()方法

> 原文:[https://www . geeksforgeeks . org/decimal format-getnegateprefix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getnegativeprefix-method-in-java/)

Java 中**十进制格式**类的 **getNegativePrefix()** 方法用于获取这个十进制格式实例的负前缀值。

**语法** :

```java
public String getNegativePrefix()

```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式实例的负前缀值。

下面程序举例说明上面的方法:

```java
// Java program to illustrate the
// getNegativePrefix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Get the negative prefix value
        String negativePrefix = deciFormat.getNegativePrefix();

        System.out.println(negativePrefix);
    }
}
```

**输出:**

```java
-

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # getnegative prefix()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getNegativePrefix())