# Java 中的 decimal format setParseBigDecimal()方法

> 原文:[https://www . geesforgeks . org/decimal format-set parsebigdecimal-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setparsebigdecimal-method-in-java/)

Java 中**十进制格式**类的 **setParseBigDecimal()** 方法用于设置十进制格式类的 parse()方法是否返回大整数类型的值。如果此方法设置为 true，则 parse()方法将返回一个大十进制值。

**语法** :

```java
public void setParseBigDecimal(boolean newValue)

```

**参数**:该方法接受布尔类型的单个参数*新值*。如果该值设置为真，则 parse()方法将返回一个大十进制值。

**返回值:**此方法不返回值。

下面的程序说明了上述方法:

**程序 1** :

```java
// Java program to illustrate the
// setParseBigDecimal() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.setParseBigDecimal(true);

        System.out.println(deciFormat.isParseBigDecimal());
    }
}
```

**输出:**

```java
true

```

**程序二** :

```java
// Java program to illustrate the
// setParseBigDecimal() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.setParseBigDecimal(false);

        System.out.println(deciFormat.isParseBigDecimal());
    }
}
```

**输出:**

```java
false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal . html # setParseBigDecimal(布尔型)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setParseBigDecimal(boolean))