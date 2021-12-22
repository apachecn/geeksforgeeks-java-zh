# Java Math nextUp()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-nextup-method-examples/](https://www.geeksforgeeks.org/java-math-nextup-method-examples/)

**java.lang.Math.nextUp()** 是 java 中的一个内置数学函数，它返回与正无穷大方向提供的参数相邻的浮点值。 **nextUp()** 方法重载，这意味着我们在 Math 类下有多个同名的方法。nextUp()的两个重载方法:

*   **双型:** nextUp(双 d)
*   **浮动类型:**下一个向上(浮动 f)

**注:**

*   如果论证是 **NaN** ，那么**的结果**就是 **NaN** 。
*   如果参数为**零**，则**结果**为**双。MIN_VALUE** 如果我们处理的是
    **双**，如果是**浮动**，那么**结果**就是**浮动。最小值**。
*   如果参数为**正无穷大**，则**结果**为**正无穷大**。

**语法:**

```java
public static dataType nextUp(dataType g)
Parameter :
 g : an input for starting floating-point value.
Return :
The nextUp() method returns the adjacent floating-point value closer to 
 positive infinity.
```

**示例:**展示 **java.lang.Math.nextUp()** 方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.nextUp() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double g = 69.19;

        // Input double value, Output adjacent floating-point
        System.out.println(Math.nextUp(g));

        float gf = 78.1f;

        // Input float value, Output adjacent floating-point
        System.out.println(Math.nextUp(gf));

        double a = 0.0 / 0;

        // Input NaN, Output NaN
        System.out.println(Math.nextUp(a));

        float b = 0.0f;

        // Input zero, Output Float.MIN_VALUE for float
        System.out.println(Math.nextUp(b));

        double c = 1.0 / 0;

        // Input positive infinity, Output positive infinity
        System.out.println(Math.nextUp(c));
    }
}
```

**输出:**

```java
69.19000000000001
78.100006
NaN
1.4E-45
Infinity

```