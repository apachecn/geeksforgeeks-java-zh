# 将一个数字四舍五入到 n 位小数的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序将一个数字四舍五入到 n 位小数/](https://www.geeksforgeeks.org/java-program-to-round-a-number-to-n-decimal-places/)

浮点数是十进制值，可以四舍五入到 n 个小数位。

**示例:**

```
Input: number = 1.41421356237, round = 3 
Output:1.414

Input: number = 0.70710678118, round = 2 
Output:0.71

```

**1。格式方法**

十进制数可以通过 Java 支持的内置 format()方法进行舍入。该方法具有以下**语法:**

```
System.out.format("%.df", number);

```

**参数:**第一个参数接受 d 位来舍入数字，第二个参数接受要舍入的数字。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Round a Number to n Decimal Places
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        double number = 3.141341435;
        // rounding number to 2 decimal places
        System.out.format("%.2f", number);
    }
}
```

**Output**

```
3.14
```

**2。十进制格式方法**

**十进制格式**是 NumberFormat 的子类，用于在 java 中执行十进制数字的格式化。我们创建这个类的一个对象，并将以#形式指定的格式作为参数传入，小数点后的#表示我们希望输出的位数。默认情况下，该数字四舍五入到最高值本身。抽取格式类的对象调用一个方法 Format()，该方法将待格式化的数字作为参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Round a Number to n Decimal Places
import java.text.DecimalFormat;
public class Decimal {

    public static void main(String[] args)
    {
        // takes in the input decimal number
        double number = 145.34567;
        // create an object of DecimalFormat class
        DecimalFormat df_obj = new DecimalFormat("#.###");

        //.format() is used to print the number in desired
        //format
        System.out.println(df_obj.format(number));
    }
}
```

**Output**

```
145.346
```

如果我们希望将数字舍入到楼层，我们调用 Java 内置类**舍入模式**。它具有以下属性值:

```
FLOOR - for next nearest floor value
CEILING - for next nearest ceiling value

```

此方法可以在支持十进制格式类的内置方法 setRoundingMode()上调用，该方法将 RoundingMode 作为参数。地板或天花板，并相应地给我们结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Round a Number to n Decimal Places
import java.math.RoundingMode;
import java.text.DecimalFormat;

public class Decimal {

    public static void main(String[] args)
    {
        // takes in the input decimal number
        double number = 9.97869896;

        // create an object of DecimalFormat class
        DecimalFormat df_obj = new DecimalFormat("#.####");

        // round number to the next lowest value
        df_obj.setRoundingMode(RoundingMode.FLOOR);

        //.format() is used to print the
        // number in desired format
        System.out.println(df_obj.format(number));
    }
}
```

**Output**

```
9.9786
```