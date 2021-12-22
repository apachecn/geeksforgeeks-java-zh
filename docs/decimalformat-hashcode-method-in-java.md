# Java 中的 DecimalFormat hashCode()方法

> 原文:[https://www . geesforgeks . org/decimal format-hashcode-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-hashcode-method-in-java/)

**hashCode()** 方法是 java 中**Java . text . DecimalFormat**类的内置方法，用于获取这个 decimal format 实例的整数 hashCode 值。

**语法** :

```java
public int hashCode()

```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个整数 hashCode 值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// hashCode() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Print the hashCode value
        System.out.println(deciFormat.hashCode());
    }
}
```

**输出:**

```java
423132

```

**程序二** :

```java
// Java program to illustrate the
// hashCode() method

import java.text.DecimalFormat;
import java.util.Currency;
import java.util.Locale;
import java.math.RoundingMode;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();
        deciFormat.getInstance(Locale.US);

        // Print the hashCode Value
        System.out.println(deciFormat.hashCode());
    }
}
```

**输出:**

```java
423132

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # hashCode()](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#hashCode())