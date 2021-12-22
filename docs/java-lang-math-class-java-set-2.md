# Java.lang.Math 类 Java |第 2 集

> 原文:[https://www . geesforgeks . org/Java-lang-math-class-Java-set-2/](https://www.geeksforgeeks.org/java-lang-math-class-java-set-2/)

[Java.lang.Math 类 Java |第 1 集](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/)

**更多方法:**

13.  **cosh() :** **java.lang.Math.cosh()** method returns the hyperbolic cosine of the argument passed.
    **Special cases :**
    *   结果是 NaN，如果参数是 NaN。
    *   如果参数为零，则结果为 1.0。
    *   如果参数为无穷大，则结果为+ve 无穷大。

    **语法:**

    ```java
    public static double cosh(double arg)
    Parameters:
    arg - The number whose hyperbolic cosine is to be returned.
    Returns:
    the hyperbolic cosine of the argument arg.

    ```

14.  **减量精确():** **java.lang.Math .减量精确()**方法将传递的参数值减 1。
    **语法:**

    ```java
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

15.  **exp() :** **java.lang.Math.exp(double arg)** method returns the Euler’s number raised to the power of double argument.
    **Important cases:**
    *   结果是 NaN，如果参数是 NaN。
    *   如果参数为+ve 无穷大，则结果为+ve 无穷大。
    *   如果参数为-ve 无穷大，则结果为+ve 零。

    **语法:**

    ```java
    public static double exp(double arg)
    Parameters:
    arg - argument passed. 
    Returns:
    Euler’s number raised to the power of passed argument

    ```

    **Java 代码，解释 lang 中的 exp()、减量 Exact()、cosh()方法。数学课。**

    ```java
    // Java program explaining lang.Math class methods
    // exp(), decrementExact(), cosh()

    import java.math.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            // Use of cosh() method
            double value = 2;
            double coshValue = Math.cosh(value);
            System.out.println("Hyperbolic Cosine of "  + coshValue);
            System.out.println("");

            // Use of decrementExact() method
            int result = Math.decrementExact(3051);
            System.out.println("Use of decrementExact() : " + result);
            System.out.println("");

            // Use of exp() method
            // declare the exponent to be used
            double exponent = 34;
            // raise e to exponent declared
            double expVal = Math.exp(exponent);
            System.out.println("Value of exp : "+ expVal);

        }
    }
    ```

    **输出:**

    ```java
    Using addExact() : 9

    acos value of Asini : NaN
    acos value of Asinj : 0.054858647341251204

    cube root : 6.0

    ```

16.  **incrementExact():****Java . lang . math . incrementExact()**方法通过增加参数的值来返回参数。

    ```java
    Syntax:
    public static int incrementExact(int arg)
                   or
    public static long incrementExact(long arg)
    Parameters:
    arg - the argument
    Returns:
    incremented value of the argument
    ```

17.  **log10():****Java . lang . math . log10()**方法返回传递的参数的 base10 对数值。

    ```java
    Syntax:
    public static double log(double arg)
    Parameters:
    arg - argument passed. 
    Returns:
    base10 logarithmic value of the argument passed.

    ```

18.  **pow() :** **java.lang.Math.pow(double b, double e)** method returns the value as **b<sup>e</sup>**

    ```java
    Syntax:
    public static double pow(double b,double e)
    Parameters:
    b : base
    e : exponent 
    Returns:
    value as base<sup>exponent</sup>

    ```

    **JAVA 代码，用 lang 解释 incrementExact()，log10()，pow()方法。数学课。**

    ```java
    // Java program explaining lang.MATH class methods
    // incrementExact(), log10(), pow()

    import java.lang.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            // Use of incrementExact() method
            int f1 = 30, f2 = -56;
            f1 =Math.incrementExact(f1);
            System.out.println("Incremented value of f1 : "+f1);

            f2 =Math.incrementExact(f2);
            System.out.println("Incremented value of f2 : "+f2);
            System.out.println("");

            // Use of log10() method
            double value = 10;
            double logValue = Math.log10(value);
            System.out.println("Log10 value of 10 : "+logValue);
            System.out.println("");

            // Use of pow() method
            double b = 10, e = 2;
            double power = Math.pow(b,e);
            System.out.println("Use of pow() : "+power);

        }
    }
    ```

    **输出:**

    ```java
    Incremented value of f1 : 31
    Incremented value of f2 : -55

    Log10 value of 10 : 1.0

    Use of pow() : 100.0

    ```

19.  **signum() :** **java.lang.Math.signum()** method returns the signum value of the argument passed.

    ```java
                                        -1    if x < 0
                        signum fun(x) =  0    if x = 0
                                         1    if x > 0

    ```

    **Note:** 

    **语法:**

    ```java
    public static double signum(double x)
                   or
    public static float signum(float x)
    Parameters:
    x - the argument whose signum value we need
    Returns:
    signum value of x

    ```

20.  **round():****Java . lang . math . round()**方法将传递的参数四舍五入到最接近的小数位数。
    **注:**结果为 0，如果自变量为 NaN。
    **语法:**

    ```java
    public static long round(long arg)
                 or
    public static double round(double arg)
    Parameters:
    arg - argument needs to round off 
    Returns:
    round off value of the argument

    ```

21.  **max() :** **java.lang.Math.max(double v1, double v2)** method returns the greater value out of the two passed argument values.
    This method just compares using magnitude without considering any sign.
    **Syntax:**

    ```java
    public static double max(double v1, double v2)
    Parameters:
    v1 - first value
    v2 - second value
    Returns:
    v1 or v2 based on which number is greater.
    It can return either of the two if v1 = v2\. 

    ```

    **Java 代码解释 lang 中 signum()，round()，max()方法。数学课。**

    ```java
    // Java code explaining the lang.Math Class methods
    // signum(), round(), max()

    import java.lang.*;
    public class NewClass
    {
        public static void main(String args[])
        {
            // Use of signum() method
            double x = 10.4556, y = -23.34789;
            double signm = Math.signum(x);
            System.out.println("Signum of 10.45  = "+signm);

            signm = Math.signum(y);
            System.out.println("Signum of -23.34 = "+signm);
            System.out.println("");

            // Use of round() method
            double r1 = Math.round(x);
            System.out.println("Round off 10.4556  = "+r1);

            double r2 = Math.round(y);
            System.out.println("Round off 23.34789 = "+r2);
            System.out.println("");

            // Use of max() method on r1 and r2
            double m = Math.max(r1, r2);
            System.out.println("Max b/w r1 and r2 = "+r2);

        }
    }
    ```

    **输出:**

    ```java
    Signum of 10.45  = 1.0
    Signum of -23.34 = -1.0

    Round off 10.4556  = 10.0
    Round off 23.34789 = -23.0

    Max b/w r1 and r2 = -23.0

    ```

22.  **log1p():****Java . lang . math . log1p()**方法返回(传递的参数+ 1)的自然对数。
    **语法:**

    ```java
    public static double log1p(double arg)
    Parameters:
    arg - the argument
    Returns:
    log of (argument + 1).
    This result is within 1 unit in the last place of exact result.

    ```

23.  **ulp() :** **java.lang.Math.ulp()** method returns **Unit of least precision(ulp)** ie. the least distance between two floating point numbers.
    Here, it is the least distance b/w the argument and next larger value.
    **Syntax:**

    ```java
    public static double ulp(double arg)
                  or
    public static float ulp(float arg)
    Parameters:
    arg - argument passed. 
    Returns:
    least distance b/w the argument and next larger value.

    ```

    **Java 代码，解释 lang 中的 ulp()，log1p()方法。数学课。**

    ```java
    // Java code explaining the lang.Math Class methods
    // ulp(), log1p()

    import java.lang.*;
    public class NewClass
    {
        public static void main(String args[])
        {
            // Use of ulp() method
            double x = 34.652, y = -23.34789;
            double u = Math.ulp(x);
            System.out.println("ulp of 34.652    : "+u);

            u = Math.ulp(y);
            System.out.println("ulp of -23.34789 : "+u);
            System.out.println("");

            // Use of log() method
            double l = 99;
            double l1 = Math.log1p(l);
            System.out.println("Log of (1 + 99)  : "+l1);

            l1 = Math.log(100);
            System.out.println("Log of 100       : "+l1);

        }
    }
    ```

    **输出:**

    ```java
    ulp of 34.652    : 7.105427357601002E-15
    ulp of -23.34789 : 3.552713678800501E-15

    Log of (1 + 99)  : 4.605170185988092
    Log of 100       : 4.605170185988092

    ```

    本文由 [<font color="green">**莫希特·古普塔 _OMG 供稿😀**</font>](https://www.facebook.com/profile.php?id=100016327034955) 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论..