# Java 中的 DecimalFormat getPositiveSuffix()方法

> 原文:[https://www . geesforgeks . org/decimal format-getpositivesuffix-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-getpositivesuffix-method-in-java/)

Java 中**十进制格式**类的 **getPositiveSuffix()** 方法用于获取这个十进制格式实例的正后缀值。

**语法** :

```
public String getPositiveSuffix()

```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回这个十进制格式实例的正后缀值。

下面程序举例说明上面的方法:

```
// Java program to illustrate the
// getPositiveSuffix() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Set a positive suffix value
        deciFormat.setPositiveSuffix("positive");

        // Get the positive suffix value
        String positiveSuffix = deciFormat.getPositiveSuffix();

        System.out.println(positiveSuffix);
    }
}
```

**输出:**

```
positive

```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/text/decimal format . html # getpositivity suffix()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#getPositiveSuffix())