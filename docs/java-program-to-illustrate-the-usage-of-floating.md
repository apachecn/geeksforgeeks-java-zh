# Java 程序演示浮动的用法

> 原文:[https://www . geesforgeks . org/Java-program-to-instruction-of-floating/](https://www.geeksforgeeks.org/java-program-to-illustrate-the-usage-of-floating/)

浮点数是那些需要分数精度的数，即可以在分数中的数。有更多的数学计算涉及到浮动类型。例如，求一个数的平方根直到某些十进制值，求该数的立方根，求二次方程的根，以及涉及三角函数如 sin cos tan 的计算。

浮点数据类型有两种

*   浮动
*   两倍

<figure class="table">

| 名字 | 宽度 | 范围 |
| --- | --- | --- |
| 浮动 | Thirty-two | 1.4e–045 至 3.4e+038 |
| 两倍 | Sixty-four | 4.9e–324 至 1.8e+308 |

</figure>

**Float** :是单精度值，存储 32 位。与双精度相比，单精度速度更快，尺寸更小。

对于 java 变量，我们可以在声明或初始化期望值为小数时使用 float。java 中的默认值是 0.0f，大小是 4 字节。java 中的 Float 可以有负值。

定义 java 浮点的正确方法和错误方法。

1.  浮点 a1=10.57f，等于 10.57
2.  浮点 a2 =10f 等于 10.0
3.  浮点 a3=9.58 它会给出一个误差。

这里我们得出结论，如果我们用 float 初始化任何值，它以 f 结尾，那么它是正确的，否则它将抛出一个错误。

**打印浮点值:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of Floating
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // initialized two float variables with
        // the least and max value of float

        float a1 = 1.40129846432481707e-45f;
        float a2 = 3.40282346638528860e+38f;

        // printed the value of a1 and a2
        System.out.println("Start range: " + a1);
        System.out.println("End range: " + a2);
    }
}
```

**Output**

```
Start range: 1.4E-45
End range: 3.4028235E38
```

**浮点值相乘:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of Floating
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // initialized two float variables a1 and a2.
        // declared n3 which will contain
        // the output of a1 * a2.

        float a1 = 10.89f;
        float a2 = 7.43f;
        float a3;

        // multiplied n1 and n2 and stored it in a3
        a3 = a1 * a2;

        // printed the value of a3
        System.out.println("The result of n1 x n2 is: "
                           + a3);
    }
}
```

**Output**

```
The result of n1 x n2 is: 80.912704
```

**用科学符号提供价值**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of Floating
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // initialized two float variables a1 and a2.
        // a1 has simple value of float type and a2
        // has the equivalent scientific notation.

        float a1 = 283.75f;
        float a2 = 2.8375e2f;

        // printed the value of a1 and a2
        System.out.println("Simple Float: " + a1);
        System.out.print("Scientific Notation: " + a2);
    }
}
```

**Output**

```
Simple Float: 283.75
Scientific Notation: 283.75
```