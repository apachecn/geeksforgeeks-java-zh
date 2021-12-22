# 用 Java 格式化的输出

> 原文:[https://www.geeksforgeeks.org/formatted-output-in-java/](https://www.geeksforgeeks.org/formatted-output-in-java/)

有时在竞争性编程中，以给定的指定格式打印输出是很重要的。大多数用户都熟悉 c 语言中的 printf 函数，我们来讨论一下如何用 Java 格式化输出:
**使用 System.out.printf()**
格式化输出这是所有方法中最简单的，因为这类似于 c 语言中的 printf，注意 System.out.print()和 System.out.println()采用单个参数，但 printf()可能采用多个参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// A Java program to demonstrate working of printf() in Java
class JavaFormatter1
{
  public static void main(String args[])
  {
    int x = 100;
    System.out.printf("Printing simple integer: x = %d\n", x);

    // this will print it upto 2 decimal places
    System.out.printf("Formatted with precision: PI = %.2f\n", Math.PI);

    float n = 5.2f;

    // automatically appends zero to the rightmost part of decimal
    System.out.printf("Formatted to specific width: n = %.4f\n", n);

    n = 2324435.3f;

    // here number is formatted from right margin and occupies a
    // width of 20 characters
    System.out.printf("Formatted to right margin: n = %20.4f\n", n);
  }
}
```

**Output**

```
Printing simple integer: x = 100
Formatted with precision: PI = 3.14
Formatted to specific width: n = 5.2000
Formatted to right margin: n =         2324435.2500

```

[System.out.format()](https://docs.oracle.com/javase/tutorial/java/data/numberformat.html) 相当于 printf()，也可以使用。

**格式化使用十进制格式类:**
十进制格式用于格式化十进制数字。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of DecimalFormat
import java.text.DecimalFormat;

class JavaFormatter2
{
  public static void main(String args[])
  {
    double num = 123.4567;

    // prints only numeric part of a floating number
    DecimalFormat ft = new DecimalFormat("####");
    System.out.println("Without fraction part: num = " + ft.format(num));

    // this will print it upto 2 decimal places
    ft = new DecimalFormat("#.##");
    System.out.println("Formatted to Give precision: num = " + ft.format(num));

    // automatically appends zero to the rightmost part of decimal
    // instead of #,we use digit 0
    ft = new DecimalFormat("#.000000");
    System.out.println("appended zeroes to right: num = " + ft.format(num));

    // automatically appends zero to the leftmost of decimal number
    // instead of #,we use digit 0
    ft = new DecimalFormat("00000.00");
    System.out.println("formatting Numeric part : num = "+ft.format(num));

    // formatting money in dollars
    double income = 23456.789;
    ft = new DecimalFormat("$###,###.##");
    System.out.println("your Formatted Dream Income : " + ft.format(income));
  }
}
```

**Output**

```
Without fraction part: num = 123
Formatted to Give precision: num = 123.46
appended zeroes to right: num = 123.456700
formatting Numeric part : num = 00123.46
your Formatted Dream Income : $23,456.79
```