# java 中的 java.math.MathContext 类

> 原文:[https://www . geesforgeks . org/Java-math-math context-class-in-Java/](https://www.geeksforgeeks.org/java-math-mathcontext-class-in-java/)

***Java . math . math context***类提供了不可变的对象，这些对象封装了上下文设置并定义了那些数字运算符规则，例如 BigDecimal 类实现的规则。

独立于基座的配置如下:

*   **精度**:一次操作要使用的位数；这一精度四舍五入到结果。
*   **舍入模式**:确定要使用的舍入算法的舍入模式对象。

> 有效位数由精度指定。舍入的默认模式是 [HALF_UP](https://www.geeksforgeeks.org/bigdecimal-setscale-method-in-java-with-examples/) 模式，这将在后面介绍。

插图:

假设选择了一个随机数，假设它是 123，现在的任务是舍入到 2 个有效数字，你将得到 120。如果你用科学符号来思考，可能会更明显。在科学符号中，123 是 1.23e2。如果你只保留 2 个有效数字，那么你得到 1.2e2，或者 120。通过减少有效位数，我们可以降低指定数字的精度。

舍入模式部分指定了我们应该如何处理精度损失。如果您使用 123 作为数字，并要求 2 个有效数字，您已经降低了重复使用该示例的准确性。舍入模式为半角向上(默认模式)，123 将变为 120。天花板圆形图案，你会得到 130。

**语法:**类声明

```java
public final class MathContext extends Object  implements Serializable
```

**施工方:**

*   ***MathContext(int setPrecision)**:*这个构造函数用指定的精度和 HALF_UP 舍入模式构造一个新的 math context。
*   ***MathContext(int setPrecision，rounding mode setRoundingMode)**:*此构造函数构造一个具有指定精度和舍入模式的新 math context。
*   ***MathContext(String val)**:*这个构造函数从一个字符串构造一个新的 math context。

现在，详细讨论一下这个类中的方法，这些方法将在程序的实现部分中使用。

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| 等于(对象 x) | This method compares this MathContext with the specified Object to see if it is equal. |
| getPrecision() | This method returns the precision setting. |
| getRoundingMode() | This method returns the RoundingMode setting. |
| hashCode() | This method returns the hash code of this MathContext. |
| toString() | This method returns the string representation of this MathContext. |

</figure>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate java.math.Context class

// Importing all classes from
// java.math package
import java.math.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Custom input number 'N' over which
        // class operation are performed
        // N = 246.8

        // erforming the rounding of operations

        // Rounding  off is carried out across
        // 4 digits
        // N = 246.8
        // It has 4 digits only so
        // the output is same as input

        // Case 1
        // Across all digits of the input N = 4
        System.out.println(new BigDecimal(
            "246.8",
            new MathContext(4, RoundingMode.HALF_UP)));

        // Case 2
        // Across 'N/2' of the input 'N'
        // Here, acrossings 2 digits as input N has 4 digits

        // Rounding HALF_UP
        System.out.println(new BigDecimal(
            "246.8",
            new MathContext(2, RoundingMode.HALF_UP)));

        // Rounding HALF_DOWN
        System.out.println(new BigDecimal(
            "246.8",
            new MathContext(2, RoundingMode.CEILING)));

        // Case 3
        // Across '1' digit of the input 'N'
        // Here, acrossings 2 digits of 4 digits of input N

        // Rounding HALF_UP
        System.out.println(new BigDecimal(
            "246.8",
            new MathContext(1, RoundingMode.HALF_UP)));

        // Rounding HALF_DOWN
        System.out.println(new BigDecimal(
            "246.8",
            new MathContext(1, RoundingMode.CEILING)));
    }
}
```

**Output**

```java
246.8
2.5E+2
2.5E+2
2E+2
3E+2
```