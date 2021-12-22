# Java 数学 IEEEremainder()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-ieeereminder-method-examples/](https://www.geeksforgeeks.org/java-math-ieeeremainder-method-examples/)

**Java . lang . math . ieeereminder()**方法按照 IEEE 754 标准的规定计算两个参数的余数运算。余数在数学上等于 f1–F2 x n，其中 n 是最接近商 f1/f2 的精确数学值的数学整数，如果两个数学整数相等地接近 f1/f2，则 n 是偶数的整数。
T3【注:

*   如果余数为零，则其符号与第一个参数的符号相同。
*   如果其中一个参数是 NaN，或者第一个参数是无穷大，或者第二个参数是正零或负零，那么结果就是 NaN。
*   如果第一个参数是有限的，第二个参数是无限的，那么结果与第一个参数相同。

**语法**:

```
public static double IEEEremainder(double dividend, double divisor)
Parameter:
dividend : the dividend.
divisor : the divisor.
Return :
This method returns the remainder when dividend is divided by divisor.

```

**例 1** :展示**Java . lang . math . ieeereminder()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.IEEEremainder() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double did1 = 31.34;
        double dis1 = 2.2;
        System.out.println(Math.IEEEremainder(did1, dis1));

        double did2 = -21.0;
        double dis2 = 7.0;

        // Sign of did2 is negative, Output is negative zero
        System.out.println(Math.IEEEremainder(did2, dis2));

        double did3 = 1.0 / 0;
        double dis3 = 0.0;

        // First argument is infinity and Second argument is zero
        // Output NaN
        System.out.println(Math.IEEEremainder(did3, dis3));

        double did4 = -2.34;
        double dis4 = 1.0 / 0;

        // First argument finite and Second argument is infinity
        // Output first argument
        System.out.println(Math.IEEEremainder(did4, dis4));
    }
}
```

输出:

```
0.5399999999999974
-0.0
NaN
-2.34

```