# Java 数学 copySign()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-copy sign-method-examples/](https://www.geeksforgeeks.org/java-math-copysign-method-examples/)

**Java . lang . math . copy sign()**方法返回第一个参数和第二个参数的符号。

**注:**
论点可以有两种类型:

*   **双式:** copySign(双 magt，双符号)
*   **浮动类型:**复制标志(浮动 magt，浮动标志)

**语法:**

```
public static double copySign(DataType magt, DataType sign)
Parameter :
 magt: argument providing the magnitude of the result.
 sign : argument providing the sign of the result.
Return :
This method returns the magnitude of the first argument with the sign of the 
second argument.
```

**示例:**展示**Java . lang . math . copy sign()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.copySign() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 34.543;
        double b = -123.44;

        // Input a, b
        // Output -34.543( a- Magnitude, b- Sign)
        System.out.println(Math.copySign(a, b));

        // Input b, a
        // Output 123.44( b- Magnitude, a- Sign)
        System.out.println(Math.copySign(b, a));

        float c = 87.56f;
        float d = -685.23f;

        // Input c, d
        // Output -87.56( c- Magnitude, d- Sign)
        System.out.println(Math.copySign(c, d));

        // Input d, c
        // Output 685.23( d- Magnitude, c- Sign)
        System.out.println(Math.copySign(d, c));
    }
}
```

**输出:**

```
-34.543
123.44
-87.56
685.23

```