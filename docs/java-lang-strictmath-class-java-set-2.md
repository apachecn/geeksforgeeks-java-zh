# Java 中的 Java.lang.StrictMath 类|第 2 集

> 原文:[https://www . geesforgeks . org/Java-lang-strict math-class-Java-set-2/](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-2/)

[Java 中的 Java.lang.StrictMath 类|集 1](https://www.geeksforgeeks.org/java-lang-strictmath-class-java-set-1/)
**Java . lang . strict math 类的更多方法**

**13。exp():Java . lang . strict math . exp(double arg)**方法返回欧拉数的双参数幂。

**重要病例:**

*   结果是 NaN，如果参数是 NaN。
*   如果参数为+ve 无穷大，则结果为+ve 无穷大。
*   如果参数为-ve 无穷大，则结果为+ve 零。

**语法:**

```
public static double exp(double arg)
Parameters:
arg - argument passed. 
Returns:
Euler’s number raised to the power of passed argument
```

**14。cosh():Java . lang . strict math . cosh()**方法返回传递的参数的双曲余弦值。

**特殊情况:**

*   结果是 NaN，如果参数是 NaN。
*   如果参数为零，则结果为 1.0。
*   如果参数为无穷大，则结果为+ve 无穷大。

**语法:**

```
public static double cosh(double arg)
Parameters:
arg - The number whose hyperbolic cosine is to be returned.
Returns:
the hyperbolic cosine of the argument arg.
```

**15。递减精确():java.lang.StrictMath .减量精确()**方法将传递的参数值递减 1。

**语法:**

```
public static int decrementExact(int arg)
                or
public static long decrementExact(long arg)
Parameters:
arg - argument passed. 
Returns:
return argument decremented by one.
Throws:
Exception if the result overflows long or int datatype, according to the
argumented data type.
```

**Java 代码，解释 lang 中的 exp()、减量 Exact()、cosh()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program explaining lang.StrictMath class methods
// exp(), decrementExact(), cosh()

import java.math.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of cosh() method
        double value = 2;
        double coshValue = StrictMath.cosh(value);
        System.out.println("Hyperbolic Cosine of " + coshValue);
        System.out.println("");

        // Use of decrementExact() method
        int result = StrictMath.decrementExact(3051);
        System.out.println("Use of decrementExact() : " + result);
        System.out.println("");

        // Use of exp() method
        // declare the exponent to be used
        double exponent = 34;
        // raise e to exponent declared
        double expVal = StrictMath.exp(exponent);
        System.out.println("Value of exp : "+ expVal);

    }
}
```

**输出:**

```
Using addExact() : 9

acos value of Asini : NaN
acos value of Asinj : 0.054858647341251204

cube root : 6.0
```

**16。log 10():Java . lang . strict math . log 10()**方法返回传递的参数的 base10 对数值。

```
Syntax:
public static double log(double arg)
Parameters:
arg - argument passed. 
Returns:
base10 logarithmic value of the argument passed.
```

**17。pow():Java . lang . strict math . pow(double b，double e)** 方法返回值为**b<sup>e</sup>T5】**

```
Syntax:
public static double pow(double b, double e)
Parameters:
b : base
e : exponent 
Returns:
value as base<sup>exponent</sup>
```

**18。incrementExact():Java . lang . strict math . incrementExact()**方法通过增加参数的值来返回参数。

```
Syntax:
public static int incrementExact(int arg)
               or
public static long incrementExact(long arg)
Parameters:
arg - the argument
Returns:
incremented value of the argument
```

**JAVA 代码，用 lang 解释 incrementExact()，log10()，pow()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program explaining lang.MATH class methods
// incrementExact(), log10(), pow()

import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of incrementExact() method
        int f1 = 30, f2 = -56;
        f1 = StrictMath.incrementExact(f1);
        System.out.println("Incremented value of f1 : " + f1);

        f2 = StrictMath.incrementExact(f2);
        System.out.println("Incremented value of f2 : " + f2);
        System.out.println("");

        // Use of log10() method
        double value = 10;
        double logValue = StrictMath.log10(value);
        System.out.println("Log10 value of 10 : " + logValue);
        System.out.println("");

        // Use of pow() method
        double b = 10, e = 2;
        double power = StrictMath.pow(b, e);
        System.out.println("Use of pow() : " + power);

    }
}
```

**输出:**

```
Incremented value of f1 : 31
Incremented value of f2 : -55

Log10 value of 10 : 1.0

Use of pow() : 100.0

```

**19。signum():Java . lang . strict math . signum()**方法返回传递的参数的 signum 值。

```
                                    -1    if x < 0
                    signum fun(x) =  0    if x = 0
                                     1    if x > 0
```

**注:**

结果是 Nan，如果通过了论证就是 NaN。

**语法:**

```
public static double signum(double x)
               or
public static float signum(float x)
Parameters:
x - the argument whose signum value we need
Returns:
signum value of x

```

**20。max():Java . lang . strict math . max(double v1，double v2)** 方法返回两个传递的参数值中较大的值。
这种方法只是比较使用量级，不考虑任何符号。

**语法:**

```
public static double max(double v1, double v2)
Parameters:
v1 - first value
v2 - second value
Returns:
v1 or v2 based on which number is greater.
It can return either of the two if v1 = v2\. 
```

**21。round():Java . lang . strict math . round()**方法将传递的参数四舍五入到最接近的小数位。

**注意:**结果为 0，如果自变量为 NaN。

**语法:**

```
public static long round(long arg)
             or
public static double round(double arg)
Parameters:
arg - argument needs to round off 
Returns:
round off value of the argument
```

**Java 代码解释 lang 中 signum()，round()，max()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code explaining the lang.StrictMath Class methods
// signum(), round(), max()

import java.lang.*;
public class NewClass
{
    public static void main(String args[])
    {
        // Use of signum() method
        double x = 10.4556, y = -23.34789;
        double signm = StrictMath.signum(x);
        System.out.println("Signum of 10.45 = " + signm);

        signm = StrictMath.signum(y);
        System.out.println("Signum of -23.34 = " + signm);
        System.out.println("");

        // Use of round() method
        double r1 = StrictMath.round(x);
        System.out.println("Round off 10.4556 = " + r1);

        double r2 = StrictMath.round(y);
        System.out.println("Round off 23.34789 = " + r2);
        System.out.println("");

        // Use of max() method on r1 and r2
        double m = StrictMath.max(r1, r2);
        System.out.println("Max b / w r1 and r2 = " + r2);

    }
}
```

**输出:**

```
Signum of 10.45  = 1.0
Signum of -23.34 = -1.0

Round off 10.4556  = 10.0
Round off 23.34789 = -23.0

Max b/w r1 and r2 = -23.0

```

**22。**方法返回**最小精度单位** ie。两个浮点数之间的最小距离。
这里，是最小距离 b/w 的自变量和下一个较大的值。

**语法:**

```
public static double ulp(double arg)
              or
public static float ulp(float arg)
Parameters:
arg - argument passed. 
Returns:
least distance b/w the argument and next larger value.
```

**23。log1p():Java . lang . strict math . log1p()**方法返回(传递的参数+ 1)的自然对数。

**语法:**

```
public static double log1p(double arg)
Parameters:
arg - the argument
Returns:
log of (argument + 1).
This result is within 1 unit in the last place of exact result.
```

**Java 代码，解释 lang 中的 ulp()，log1p()方法。StrictMath 类。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code explaining the lang.StrictMath Class methods
// ulp(), log1p()

import java.lang.*;
public class NewClass
{
    public static void main(String args[])
    {
        // Use of ulp() method
        double x = 34.652, y = -23.34789;
        double u = StrictMath.ulp(x);
        System.out.println("ulp of 34.652 : " + u);

        u = StrictMath.ulp(y);
        System.out.println("ulp of -23.34789 : " + u);
        System.out.println("");

        // Use of log() method
        double l = 99;
        double l1 = StrictMath.log1p(l);
        System.out.println("Log of (1 + 99) : " + l1);

        l1 = StrictMath.log(100);
        System.out.println("Log of 100     : " + l1);

    }
}
```

**输出:**

```
ulp of 34.652    : 7.105427357601002E-15
ulp of -23.34789 : 3.552713678800501E-15

Log of (1 + 99)  : 4.605170185988092
Log of 100       : 4.605170185988092

```