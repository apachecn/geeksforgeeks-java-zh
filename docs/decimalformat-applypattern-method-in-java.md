# Java 中的 DecimalFormat applyPattern()方法

> 原文:[https://www . geesforgeks . org/decimal format-apply pattern-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-applypattern-method-in-java/)

Java 中 DecimalFormat 类的 applyPattern()方法用于将给定的字符串模式应用于这个 Decimal 格式。这个模式可以由用户设置。

**语法** :

```java
public void applyPattern(String pattern)

```

**参数**:该方法采用一个字符串类型的参数模式，并引用将用于格式化十进制模式的模式。

**返回值**:该方法返回 void 类型。

下面的程序说明了 applyPattern()方法的工作原理:

**程序 1** :

```java
// Java program to illustrate the
// applyPattern method

import java.text.DecimalFormat;

public class Main {
    public static void main(String[] args)
    {

        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.applyPattern("##, ##");
        System.out.println(deciFormat.format(-123456789.54321));
    }
}
```

**输出:**

```java
-1, 23, 45, 67, 90

```

**程序二** :

```java
// Java program to illustrate the
// applyPattern method

import java.text.DecimalFormat;

public class Main {
    public static void main(String[] args)
    {

        DecimalFormat deciFormat = new DecimalFormat();

        deciFormat.applyPattern("#, #00.0#");
        System.out.println(deciFormat.format(-123456789.54321));
    }
}
```

**输出:**

```java
-123, 456, 789.54

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # https://docs . Oracle . com/javase/7/docs/API/Java/text/decimal format . html # apply pattern(Java . lang . string)(Java . lang . string)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#applyPattern(java.lang.String)(java.lang.String))