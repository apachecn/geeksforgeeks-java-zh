# 实现帕克-米勒随机数生成算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-park-miller-随机数生成-算法/](https://www.geeksforgeeks.org/java-program-to-implement-park-miller-random-number-generation-algorithm/)

**Park–Miller**随机数发生器也被称为**莱默随机数发生器**。这种类型的随机数发生器(RNG)的一般公式是，X <sub>k+1</sub> = a * x <sub>k</sub> mod m

其中模 **m** 是素数或素数的幂，乘数 **a** 是以 m 为模的高乘法阶元素，**种子 X<sub>0</sub>T8】是 m 的互质**

**帕克-米勒算法**

1)将变量 m、a、q、r 和 r_seed(X <sub>0</sub> )声明为常量变量并赋值

```java
m = 2145678965L;
a = 48271L;
q = 44488L;
r = 3399L;
r_seed = 12345678L
```

这里，常数 m 和 r_seed 的值以这样的方式选择，即 **GCD(m，r_seed) = 1** 。模数也可以选择为素数，使得互素种子的选择变得微不足道(任何 0<*X*<sub>0</sub><T9*m*都行)。这里 **a** 、 **q** 、 **r** 为常数。

2)用 double 作为返回类型声明函数统一。

2.1)声明变量 hi、lo、t

2.2)如下设置变量 hi、lo、t:

2.2.1) hi=作为种子除以 b

2 . 2 . 2)lo = seed–b * hi

2 . 2 . 3)t = a* lo–c * hi

其中 **hi** 和 **li** 分别是特定 m 和 r_seed(X <sub>0</sub> 的随机数范围内的最高和最低数字。

2.3)检查是否(t > 0)即:生成的随机数为正，则设置 **r_seed = t** 。

2.4)否则设置 **r_seed = t + m** 。//生成的随机数为负数

2.5)从函数 uniform 返回种子。

3)在主要方法中

3.1)从 i=0 到 10 开始循环

3.1.1)随机调用函数，并存储每次迭代的结果。

3.2)打印结果

5)结束

**示例:**下面的程序实现了 Park-Miller 随机数生成算法。

**注意:**这段代码的每次迭代都会产生不同的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java implementation of Park-Miller algorithm

public class Park_Miller_Random_Numbers {

    // m is coprime to seed r_seed
    static final long m = 2147483647L;

    // constants
    static final long a = 48271L;
    static final long q = 44488L;
    static final long r = 3399L;

    // take a r_seed that is coprime to m
    static long r_seed = 12345678L;

    public static double uniform()
    {
        // highest and lowest for
        // a random number generation
        // range
        long hi = r_seed / q;
        long lo = r_seed - q * hi;

        // calculate random number
        long t = a * lo - r * hi;

        // if positive
        if (t > 0)
            r_seed = t;
        else
            r_seed = t + m;
        return r_seed;
    }

    public static void main(String[] argv)
    {
        double[] A = new double[10];

        for (int i = 0; i < 5; i++)
            A[i] = uniform();

        for (int i = 0; i < 5; i++)
            System.out.print("  " + A[i]);
    }
}
```

**Output**

```java
  1.085252519E9  5.08259731E8  1.352291773E9  1.563240271E9  8.90733155E8
```