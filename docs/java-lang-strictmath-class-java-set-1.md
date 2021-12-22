# Java 中的 Java.lang.StrictMath 类|第 1 集

> 原文:[https://www . geesforgeks . org/Java-lang-strict math-class-Java-set-1/](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)

**StrictMath 类**方法有助于执行数值运算，如平方、平方根、立方、立方根、指数和三角运算

**申报:**

```java
public final class StrictMath
   extends Object
```

**NaN 论证？**
一个持有双精度型非数字值的常数。它相当于 double . longbittodouble(0x7ff 800000000000001)返回的值。

**法郎数学类:**
**1。acos():**[**Java . lang . strict math . acos()**](https://www.geeksforgeeks.org/strictmath-acos-method-in-java/)方法返回传递的参数的弧余弦值。
弧余弦是传递的参数的反余弦。
acos(arg) = cos <sup>-1</sup> 的 arg

**特例:**结果为 NaN，如果自变量为 NaN 或其绝对值大于 1。

**语法:**

```java
public static double acos(double a)
Parameters:
a - the argument whose arc cosine value we need.
    argument is taken as radian    
Returns:
arc cosine value of the argument.
```

**2。ABS():Java . lang . strict math . ABS()**方法返回传递的任何类型参数的绝对值。这个方法可以处理所有的数据类型。

*   如果参数为正零或负零，则结果为正零。
*   如果参数为无穷大，则结果为正无穷大。
*   结果是 NaN，如果传递的参数是 NaN。

**语法:**

```java
public static datatype abs(datatype arg)
Parameters:
arg - the argument whose absolute value we need
Returns:
absolute value of the passed argument.
```

**3。tora dians():Java . lang . strict math . tora dians(double deg)**方法将参数(度数)转换为弧度。
**注:** StrictMath 类通常将弧度作为输入，这在实际应用中有很大不同，因为角度通常以度数表示。

**语法:**

```java
public static double toRadians(double deg)
Parameters:
deg - degree angle needs to be in radian.
Returns:
radians equivalent of the degree-argument passed.
```

**Java 代码解释在 lang 中的 abs()、acos()、toRadians()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program explaining lang.StrictMath class methods
// abs(), acos(), toRadians()

import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Declaring the variables
        int Vali = -1;
        float Valf = .5f;

        // Printing the values
        System.out.println("Initial value of int  : " + Vali);
        System.out.println("Initial value of int  : " + Valf);

        // Use of .abs() method to get the absoluteValue
        int Absi = StrictMath.abs(Vali);
        float Absf = StrictMath.abs(Valf);

        System.out.println("Absolute value of int : " + Absi);
        System.out.println("Absolute value of int : " + Absf);
        System.out.println("");

        // Use of acos() method
        // Value greater than 1, so passing NaN
        double Acosi = StrictMath.acos(60);
        System.out.println("acos value of Acosi : " + Acosi);
        double x = StrictMath.PI;

        // Use of toRadian() method
        x = StrictMath.toRadians(x);
        double Acosj = StrictMath.acos(x);
        System.out.println("acos value of Acosj : " + Acosj);

    }
}
```

**输出:**

```java
Initial value of int  : -1
Initial value of int  : 0.5
Absolute value of int : 1
Absolute value of int : 0.5

acos value of Acosi : NaN
acos value of Acosj : 1.5159376794536454
```

**4。cbrt():**[**Java . lang . strict math . cbrt()**](https://www.geeksforgeeks.org/strictmath-cbrt-method-in-java/)方法返回传递的参数的立方根。

**特殊点:**

*   结果是 NaN，如果参数是 NaN。
*   如果参数是无限的，则结果是一个与参数符号相同的无穷大。
*   如果参数为零，则结果为零。

**语法:**

```java
public static double cbrt(double arg)
Parameters:
arg - argument passed. 
Returns:
cube root of the argument passed
```

**5。asin():**[**Java . lang . strict math . asin()**](https://www.geeksforgeeks.org/strictmath-asin-method-in-java-with-examples/)方法返回传递的方法参数的反正弦值。返回的角度在-pi/2 到 pi/2 的范围内。
反正弦是传递的参数的反正弦。
asin(arg) =正弦 <sup>-1</sup> 的 arg

**特殊情况:**

*   如果参数为 NaN 或其绝对值大于 1，则结果为 NaN。
*   如果参数为零，则结果为零。

**语法:**

```java
public static double asin(double arg)
Parameters:
arg - argument passed. 
Returns:
arc sine of the argument passed.
```

**Java 代码解释 lang 中的 asin()，cbrt()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program explaining lang.StrictMath class methods
// asin(), cbrt()

import java.lang.*;
public class NewClass
{

    public static void main(String[] args)
    {
        int a = 1, b = 8;
        int radd = a + b;

        // Use of asin() method
        // Value greater than 1, so passing NaN
        double Asini = StrictMath.asin(radd);
        System.out.println("asin value of Asini : " + Asini);
        double x = StrictMath.PI;

        // Use of toRadian() method
        x = StrictMath.toRadians(x);
        double Asinj = StrictMath.asin(x);
        System.out.println("asin value of Asinj : " + Asinj);
        System.out.println("");

        // Use of cbrt() method
        double cbrtval = StrictMath.cbrt(216);
        System.out.println("cube root : " + cbrtval);

    }
}
```

**输出:**

```java
asin value of Asini : NaN
asin value of Asinj : 0.054858647341251204

cube root : 6.0
```

**6。log():Java . lang . strict math . log()**方法返回传递的参数的对数值。

```java
Syntax:
public static double log(double arg)
Parameters:
arg - argument passed. 
Returns:
logarithmic value of the argument passed.
```

**7。hypot():Java . lang . strict math . hypot(double p，double b)** 方法返回直角三角形的斜边在经过 traingle 的底边和垂线时作为自变量。
**斜边=【垂直 <sup>2</sup> +底座<sup>2</sup><sup>1/2</sup>**

**要点:**

*   如果任一参数为无穷大，则结果为正无穷大。
*   如果任一参数为 NaN，且任一参数都不是无穷大，则结果为 NaN。

```java
Syntax:
public static double hypot(double p, double b)
Parameters:
p - perpendicular of the right triangle
b - base of the right triangle
Returns:
hypotenuse of the right triangle
```

**8。floor():**[**Java . lang . strict math . floor()**](https://www.geeksforgeeks.org/strictmath-floor-method-in-java/)方法返回参数的 floor 值，即小于或等于传递的参数的最接近的整数值。
例如:101.23 的地板值= 101

**重要提示:**如果通过了安南或无限参数，会产生相同的参数。

```java
Syntax:
public static double floor(double arg)
Parameters:
arg - the argument whose floor value we need
Returns:closest possible value that is either less than 
                or equal to the argument passed
```

**9。**方法通过对两个参数 w.r.t IEEE 754 标准应用余数运算，返回余数值。
余值=**D1–D2 * n**
其中，
n = D1/D2 的最接近精确值

```java
Syntax:
public static double IEEEremainder(double d1, double d2)
Parameters:
d1 - dividend 
d2 - divisor
Returns:
remainder when f1(dividend) is divided by(divisor)
```

**Java 代码解释 floor()，hypot()，IEEEremainder()，log()方法中的 lang。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program explaining lang.MATH class methods
// floor(), hypot(), IEEEremainder(), log()

import java.lang.*;
public class NewClass
{

    public static void main(String[] args)
    {
        // Use of floor method
        double f1 = 30.56, f2 = -56.34;
        f1 = StrictMath.floor(f1);
        System.out.println("Floor value of f1 : " + f1);

        f2 = StrictMath.floor(f2);
        System.out.println("Floor value of f2 : "  + f2);
        System.out.println("");

        // Use of hypot() method
        double p = 12, b = -5;
        double h = StrictMath.hypot(p, b);
        System.out.println("Hypotenuse : "+h);
        System.out.println("");

        // Use of IEEEremainder() method
        double d1 = 105, d2 = 2;
        double r = StrictMath.IEEEremainder(d1, d2);
        System.out.println("Remainder : " + r);
        System.out.println("");

        // Use of log() method
        double l = 10;
        l = StrictMath.log(l);
        System.out.println("Log value of 10 : " + l);

    }
}
```

**输出:**

```java
Floor value of f1 : 30.0
Floor value of f2 : -57.0

Hypotenuse : 13.0

Remainder : 1.0

Log value of 10 : 2.302585092994046
```

**10。ceil():**[**Java . lang . strict math . ceil(double a)**](https://www.geeksforgeeks.org/strictmath-ceil-method-in-java-with-examples/)方法返回大于或等于传递的参数的最小可能值。返回值是一个数学整数。

*   如果返回值已经是数学整数，则结果相同。
*   如果传递的参数是 NaN、无穷大或零，则结果相同。
*   如果传递的参数小于零但大于-1.0，则结果为负零

**语法:**

```java
public static double ceil(double arg)
Parameters:
arg - the argument value
Returns:
smallest possible value(mathematical integer)
which is either greater or equal to the argument passed
```

**11 时。copy sign():Java . lang . strict math . copy sign()**方法返回第一个浮点参数，但第二个参数有符号。

**语法:**

```java
public static double copySign(double m, double s)
                    or
public static float copySign(float m, float s)
Parameters:
m - magnitude 
s - sign 
Returns:
returns second argument with sign of first floating-point argument.
```

**12 时。atan():**[**Java . lang . strict math . atan()**](https://www.geeksforgeeks.org/strictmath-atan-method-in-java/)方法返回返回方法参数值的反正切。返回的角度在-π/2 到π/2 的范围内。
弧谭是逆谭的论点通过了。
atan(arg)= arg 的 tan 逆

**特殊情况:**

*   如果传递的参数是 NaN 或其绝对值大于 1，则结果是 NaN。
*   如果参数为零，则结果为零。

**语法:**

```java
public static double atan(double a)
Parameters:
a - the argument whose arc tangent value we need.
    argument is taken as radian
Returns:
arc tan value of the argument.
```

**Java 代码，用 lang 解释 atan()、ceil()、copySign()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program explaining lang.StrictMath class methods
// atan(), ceil(), copySign()

import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of atan() method
        double Atani = StrictMath.atan(0);
        System.out.println("atan value of Atani : " + Atani);
        double x = StrictMath.PI / 2;

        // Use of toRadian() method
        x = StrictMath.toRadians(x);
        double Atanj = StrictMath.atan(x);
        System.out.println("atan value of Atanj : " + Atanj);
        System.out.println("");

        // Use of ceil() method
        double val = 15.34, ceilval;
        ceilval = StrictMath.ceil(val);
        System.out.println("ceil value of val : " + ceilval);
        System.out.println("");

        double dblMag = val;
        double dblSign1 = 3;
        double dblSign2 = -3;

        // Use of copySign() method
        double result1 = StrictMath.copySign(dblMag, dblSign1);
        System.out.println("copySign1 : " + result1);

        double result2 = StrictMath.copySign(dblMag, dblSign2);
        System.out.println("copySign2 : " + result2);

    }
}
```

**输出:**

```java
atan value of Atani : 0.0
atan value of Atanj : 0.0274087022410345

ceil value of val : 16.0

copySign1 : 15.34
copySign2 : -15.34
```

**参考更多郎的方法。位于:** [的 StrictMath 类 JAva.lang.StrictMath 类 Java | Set 2](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-2/)
本文由 [**Mohit Gupta_OMG 供稿😀**](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。