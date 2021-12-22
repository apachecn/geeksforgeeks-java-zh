# Java 数学 nextAfter()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-next after-method-example/](https://www.geeksforgeeks.org/java-math-nextafter-method-example/)

**Java . lang . math . nextafter()**返回第二个参数方向上与第一个参数相邻的浮点数。如果两个参数相等，则返回第二个参数。

> **语法:**
> //数据类型可以是**浮点**或**双**。
> 公共静态数据类型 nextAfter(数据类型 st，数据类型 dir)
> 
> **参数:**
> **st :** 起始浮点值。
> **dir :** 指示应该返回 start 的哪个邻居或 start 的值。
> 
> **返回:**
> 这个方法返回方向方向上与开始相邻的浮点数。

**注:**

*   如果其中一个**参数**是 **NaN** ，那么输出就是 **NaN**
*   如果两个参数都是**带符号的零**，则返回方向不变(如果两个参数相等，则返回第二个参数的要求暗示了这一点)。
*   如果**开始**是**加倍。最小值或浮动值。MIN_VALUE** 和 direction 的值应使结果具有较小的幅度，然后返回一个符号与 start 相同的**零点**。
*   如果**开始**是**无穷大**并且方向有一个值使得结果应该有一个较小的量级，**加倍。最大值或浮动。返回与开始符号相同的最大值**。
*   如果**开始**等于**加倍。最大值或浮动。最大值**和方向的值应使结果具有更大的幅度，返回符号与开始相同的**无穷大**。

**例 1 :** 展示**Java . lang . math . next after()**方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.nextAfter() method
import java.lang.Math;

class GfG {

    // driver code
    public static void main(String args[])
    {
        double a = 0.0 / 0;
        double b = 12.2;

        // Input a is NaN, Output NaN
        System.out.println(Math.nextAfter(a, b));

        double c = 0.0;
        double d = 0.0;

        // Both Input are signed zeros, Output zero
        System.out.println(Math.nextAfter(c, d));

        float e = Float.MIN_VALUE;
        float f = 12.2f;

        System.out.println(Math.nextAfter(e, f));

        float g = 1.0f / 0f;
        float h = 1.0f;

        System.out.println(Math.nextAfter(g, h));

        double i = Double.MAX_VALUE;
        double j = 12344.2;

        System.out.println(Math.nextAfter(i, j));
    }
}
```

**输出:**

```java
NaN
0.0
2.8E-45
3.4028235E38
1.7976931348623155E308

```