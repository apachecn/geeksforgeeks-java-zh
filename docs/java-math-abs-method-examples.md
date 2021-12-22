# Java 数学 abs()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-ABS-method-examples/](https://www.geeksforgeeks.org/java-math-abs-method-examples/)

绝对值是指与参数中传递的数字相对应的正值。现在，极客你一定想知道它到底是什么意思，所以它被引用了，不管它是正的还是负的数字，在这两种情况下，计算都会发生在正的对应数字上。所以为了计算任何数字的绝对值，我们在 Java 中有一个指定的方法，称为 **abs()** 存在于[数学类](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/)中，存在于 java.lang 包中。

**java.lang.Math.abs()** 返回给定参数的绝对值。

*   如果该参数不是负数，则返回该参数。
*   如果参数为负，则返回参数的否定。

**语法:**

```java
public static DataType abs(DataType a)
```

**参数:** Int、long、float 或 double 值，其绝对值待定

**返回类型:**这个方法返回参数的绝对值。

**异常抛出:**T2】算术异常

> **提示:**必须知道泛型返回类型，如下所示:
> 
> *   **如果参数是双精度型或浮点型:**
>     *   如果参数为正零或负零，则结果为正零。
>     *   如果参数是无限的，结果就是正无穷大。
>     *   如果参数是 NaN，结果就是 NaN。
> *   **如果参数是 int 或 long 类型:**如果参数等于 Integer 的值。最小值或长值。MIN_VALUE，最负的可表示整数或长值，结果是相同的值，为负。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Absolute Method
// of Math Class

// Importing all Math classes
// from java.lang package
import java.lang.Math;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom integer input received from user
        int n = -7;

        // Printing value before applying absolute function
        System.out.println(
            "Without applying Math.abs() method : " + n);

        // Applying absolute math function and
        // storing it in integer variable
        int value = Math.abs(n);

        // Printing value after applying absolute function
        System.out.println(
            "With applying Math.abs() method : " + value);
    }
}
```

**Output**

```java
Without applying Math.abs() method : -7
With applying Math.abs() method : 7
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Working of abs() method
// of Math class inside java.lang package

// Importing Math class
// from java.lang package
import java.lang.Math;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Customly declaring and initializing all
        // arguments that ans() function takes

        // Float
        float a = 123.0f;
        float b = -34.2323f;

        // Double
        double c = -0.0;
        double d = -999.3456;

        // Integer
        int e = -123;
        int f = -0;

        // Long
        long g = -12345678;
        long h = 98765433;

        // abs() method taking float type as input
        System.out.println(Math.abs(a));
        System.out.println(Math.abs(b));

        // abs() method taking double type as input
        System.out.println(Math.abs(1.0 / 0));
        System.out.println(Math.abs(c));
        System.out.println(Math.abs(d));

        // abs() method taking int type as input
        System.out.println(Math.abs(e));
        System.out.println(Math.abs(f));
        System.out.println(Math.abs(Integer.MIN_VALUE));

        // abs() method taking long type as input
        System.out.println(Math.abs(g));
        System.out.println(Math.abs(h));
        System.out.println(Math.abs(Long.MIN_VALUE));
    }
}
```

**Output**

```java
123.0
34.2323
Infinity
0.0
999.3456
123
0
-2147483648
12345678
98765433
-9223372036854775808
```