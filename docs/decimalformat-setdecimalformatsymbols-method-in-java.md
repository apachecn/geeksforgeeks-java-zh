# Java 中的 decimal format set decimal format symbols()方法

> 原文:[https://www . geesforgeks . org/decimal format-setdecimal format symbols-method-in-Java/](https://www.geeksforgeeks.org/decimalformat-setdecimalformatsymbols-method-in-java/)

**设置抽取格式符号()**方法是 java 中 **java.text .抽取格式**类的内置方法，用于为此抽取格式实例设置新的抽取格式符号。程序员或用户不能更改此十进制格式符号。

**语法** :

```java
public void setDecimalFormatSymbols(DecimalFormatSymbols newSymbols)

```

**参数**:该函数接受单个参数*新符号*，这是用于为此实例设置新十进制格式符号的十进制格式符号实例。

**返回值**:函数不返回值。

下面是上述功能的实现:

**程序 1** :

```java
// Java program to illustrate the
// setDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Get the DecimalFormatSymbols Instance
        DecimalFormatSymbols dfs = deciFormat.getDecimalFormatSymbols();

        // Set the DecimalFormatSymbols
        deciFormat.setDecimalFormatSymbols(dfs);

        System.out.println(deciFormat.format(12345.6789));
    }
}
```

**输出:**

```java
12, 345.679

```

**程序二** :

```java
// Java program to illustrate the
// setDecimalFormatSymbols() method

import java.text.DecimalFormat;
import java.text.DecimalFormatSymbols;
import java.util.Currency;
import java.util.Locale;

public class Main {
    public static void main(String[] args)
    {

        // Create the DecimalFormat Instance
        DecimalFormat deciFormat = new DecimalFormat();

        // Get the DecimalFormatSymbols Instance
        DecimalFormatSymbols dfs = deciFormat.getDecimalFormatSymbols();
        dfs.setZeroDigit('\u0660');

        // Set the DecimalFormatSymbols
        deciFormat.setDecimalFormatSymbols(dfs);

        System.out.println(deciFormat.format(12345.6789));
    }
}
```

**输出:**

```java
??, ???.???

```

**参考**:[https://docs . Oracle . com/javae/7/docs/API/Java/text/decimal format . html # setdecimal format symbols(Java . text . decimal format symbols)](https://docs.oracle.com/javase/7/docs/api/java/text/DecimalFormat.html#setDecimalFormatSymbols(java.text.DecimalFormatSymbols))