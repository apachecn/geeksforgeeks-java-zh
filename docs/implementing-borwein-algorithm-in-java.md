# 在 Java 中实现 Borwein 算法

> 原文:[https://www . geesforgeks . org/impering-bor wein-algorithm in-Java/](https://www.geeksforgeeks.org/implementing-borwein-algorithm-in-java/)

Borwein 的算法是 Jonathan 和 Peter Borwein 为计算 1/π的估计而设计的计算。他们构思了一些不同的算法。然而，以下在 Java 中用四次汇编实现 Borwein 算法实际上确定了 Pi，收敛速度过快。原则上，a 将四次幂合并到 1/π。每强调一次，正确数字的数量就这样翻了两番。

java 的数学库用于实现 Borwein 算法，该算法是库的幂和根函数，即 [*【数学幂()*](https://www.geeksforgeeks.org/math-pow-method-in-java-with-example/) *。*[**Java . lang . math**](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/)**。pow()** 用于计算一个数与其他数的幂的乘积。该函数接受两个参数，并将第一个参数的值返回给第二个参数。

在一个实现中，数学模块使用了两个内置函数，如下所示:

1.  电源功能: [***电源()***T5】](https://www.geeksforgeeks.org/math-pow-method-in-java-with-example/)
2.  平方根函数:[***【sqrt()***](https://www.geeksforgeeks.org/java-sqrt-method-examples/)

**1。power()功能**

**语法**:

```
public static double pow(double a, double b) ;
```

**参数**:

*   **a:** 要返回幂根的基值。
*   **b:** 要返回的指数值。

**返回**:此方法返回 a <sup>b</sup> 。

**2。sqrt()** ***功能***

[*【数学 sqrt()】*](https://www.geeksforgeeks.org/java-sqrt-method-examples/)*Java . lang . Math . sqrt()返回作为参数传递给它的 double 类型的值的平方根。*

***语法**:*

```
*public static double sqrt(double a) ;*
```

***参数:**要返回平方根的值。*

***Return:** 这个方法返回传递给它的参数的正平方根值。*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java program to implement Borwein Algorithm

// Importing generic java classes
import java.io.*;

class GFG {

    // Main driver method
    public double Borwein(int noOfIter)
    {
        // Calculating initial value of 1/pi
        double oneByPi = 6.0 - 4 * Math.sqrt(2);

        // Calculating the constant value y
        // used in Borwein Algorithm
        double y = Math.sqrt(2) - 1.0;

        double oneByPiAfterIter;
        double yAfterIter;

        // It calculates an estimation
        // of 1/pi that increases in accurary
        // the more iterations you use
        for (int i = 0; i < noOfIter; i++) {

            // Based on Algorithm formulas are used
            yAfterIter= (1 - Math.pow((1 - y * y * y * y), (0.25))) /
                          (1+ Math.pow((1 - y * y * y * y), (0.25)));

            oneByPiAfterIter = oneByPi * Math.pow((1 + yAfterIter), 4) - 
            Math.pow(2, 2 * i + 3) * yAfterIter * (1 + yAfterIter + 
                                           yAfterIter * yAfterIter);

            y = yAfterIter;

            oneByPi = oneByPiAfterIter;
        }
        return oneByPi;
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Object of above class in main
        GFG ob = new GFG();

        // Number of Iteration
        int noOfIter = 10;

        // Printing value of 1/pi
        System.out.println("Value of 1/pi : "
                        + ob.Borwein(noOfIter));
    }
}*
```

***输出:***

```
*Value of 1/pi : 0.31830988618379075*
```