# Java 中的 DecimalFormat setPositivePrefix()方法

> 原文:[https://www . geesforgeks . org/decimal format-set positiveprefix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setpositiveprefix-method-in-java/)

Java 中**十进制格式**类的**设置正前缀()**方法用于为此十进制格式实例设置正前缀值。

**语法** :

```
public void setPositivePrefix(String newValue)

```

**参数**:此方法使用单个参数*新值*，该新值将被设置为此十进制格式实例的正前缀。

**返回值:**此方法不返回值。

下面程序举例说明上面的方法:

```
// Java program to illustrate the
// setPositivePrefix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a positive prefix value
        deciFormat.setPositivePrefix("positive");

        // Print a number with positive prefix
        System.out.println(deciFormat.format(12345));
    }
}
```

**输出:**

```
positive12, 345

```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/text/decimal format . html # set context prefix(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setPositivePrefix(java.lang.String))