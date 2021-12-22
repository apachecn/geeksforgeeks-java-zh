# java 中的 java.lang.Math.atan2()

> 原文:[https://www.geeksforgeeks.org/java-lang-math-atan2-java/](https://www.geeksforgeeks.org/java-lang-math-atan2-java/)

**atan2()** 是 Java 中的一个内置方法，用于从极坐标返回θ分量。atan2()方法返回一个介于–![\pi  ](img/666cf0b3bde62050966bf6eee72ffde2.png "Rendered by QuickLaTeX.com")和![\pi  ](img/666cf0b3bde62050966bf6eee72ffde2.png "Rendered by QuickLaTeX.com")之间的数值，代表(x，y)点和正 x 轴的角度![\theta  ](img/b5e04cb8ab03d9b0e599fd3290012ddb.png "Rendered by QuickLaTeX.com")。它是正 X 轴和点(X，y)之间的逆时针角度，以弧度为单位。
**语法:**

```
Math.atan2(double y, double x)
where, x and y are X and Y coordinates in double data type.
```

**返回:**
返回一个双精度值。双值为极坐标(r，θ)的![\theta  ](img/b5e04cb8ab03d9b0e599fd3290012ddb.png "Rendered by QuickLaTeX.com")。
**示例:**演示 atan2()方法的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for implementation of
// atan2() method
import java.util.*;
class GFG {

    // Driver Code
    public static void main(String args[])
    {

        // X and Y coordinates
        double x = 90.0;
        double y = 15.0;

        // theta value from polar coordinate (r, theta)
        double theta = Math.atan2(y, x);

        System.out.println(theta);
    }
}
```

**Output**

```
0.16514867741462683

```