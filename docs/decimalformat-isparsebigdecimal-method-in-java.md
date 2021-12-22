# Java 中的 DecimalFormat isParseBigDecimal()方法

> 原文:[https://www . geesforgeks . org/decimal format-isparsebigdecimal-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-isparsebigdecimal-method-in-java/)

Java 中**十进制格式**类的 **isParseBigDecimal()** 方法用于检查十进制格式类的 parse()方法是否返回大整数类型的值。

**语法** :

```java
public boolean isParseBigDecimal()

```

**参数**:该方法不接受任何参数。

**返回值:**这个方法返回一个布尔值。如果解析方法返回大十进制值，则返回真，否则返回假。

下面的程序说明了上述方法:

**程序 1** :

```java
// Java program to illustrate the
// isParseBigDecimal() method

import java.text.DecimalFormat;

public class GFG {

    public static void main(String[] args)
    {

        // Create a DecimalFormat instance
        DecimalFormat deciFormat = new DecimalFormat();

        System.out.println(deciFormat.isParseBigDecimal());
    }
}
```

**输出:**

```java
false

```

**程序二** :

```java
// Java program to illustrate the
// isParseBigDecimal() method

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

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal . html # isParseBigDecimal()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#isParseBigDecimal())