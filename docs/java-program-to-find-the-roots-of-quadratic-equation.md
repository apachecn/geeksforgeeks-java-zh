# 寻找二次方程根的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序查找二次方程的根/](https://www.geeksforgeeks.org/java-program-to-find-the-roots-of-quadratic-equation/)

函数的根是 x 截距。根据定义，位于 x 轴上的点的 y 坐标是 **零** 。因此，要求一个二次函数的根，我们设 f (x) = 0，求解方程，ax <sup>2</sup> + bx + c = 0。

**二次方程的条件–**

```java
ax^2 + bx + c = 0 

where 
a, b, c are real numbers and cannot be zero ie, there value must be from {-∞ to -1} and {1 to ∞}
```

**求二次方程根的数学公式–**

```java
roots = (-b ± √(b2-4ac)) / (2a)

± represents there are two roots.
```

**二次方程的根是–**

```java
first = (-b + √(b2-4ac)) / (2a)
second = (-b - √(b2-4ac)) / (2a)
```

**行列式的(b^2–4ac)告诉我们根的性质–**

1.  If **(b 2–4ac) > 0** , the roots are real and different.
2.  If **(b 2–4ac) = = 0** , the roots are real and equal.
3.  If **(b 2–4ac) < 0** , the roots are complex and different.

**代码求一个二次方程的根:**

## Java

```java
// Java program to find the roots of
// quadratic equation

public class Main {

    public static void main(String[] args)
    {

        // value of the constants a, b, c
        double a = 7.2, b = 5, c = 9;

        // declared the two roots
        double firstroot, secondroot;

        // determinant (b^2 - 4ac)
        double det = b * b - 4 * a * c;

        // check if determinant is greater than 0
        if (det > 0) {

            // two real and distinct roots
            firstroot = (-b + Math.sqrt(det)) / (2 * a);
            secondroot = (-b - Math.sqrt(det)) / (2 * a);

            System.out.format(
                "First Root = %.2f and Second Root = %.2f",
                firstroot, secondroot);
        }

        // check if determinant is equal to 0
        else if (det == 0) {

            // two real and equal roots
            // determinant is equal to 0
            // so -b + 0 == -b
            firstroot = secondroot = -b / (2 * a);

            System.out.format(
                "First Root = Second Root = %.2f;",
                firstroot);
        }

        // if determinant is less than zero
        else {

            // roots are complex number and distinct
            double real = -b / (2 * a);

            double imaginary = Math.sqrt(-det) / (2 * a);

            System.out.printf("First Root = %.2f+%.2fi",
                              real, imaginary);
            System.out.printf("\nSecond Root = %.2f-%.2fi",
                              real, imaginary);
        }
    }
}
```

**输出**

```java
First Root = -0.35+1.06i
Second Root = -0.35-1.06i
```