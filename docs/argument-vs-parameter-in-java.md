# Java 中的参数 vs 参数

> 原文:[https://www . geesforgeks . org/argument-vs-parameter-in-Java/](https://www.geeksforgeeks.org/argument-vs-parameter-in-java/)

**参数**

参数是调用函数时传递给函数的值。每当在程序执行期间调用任何函数时，都会有一些值随函数传递。这些值被称为**参数**。当参数与函数一起传递时，它会替换那些在函数定义过程中使用的变量，然后用这些值执行函数。让我们看一些容易理解的例子:

**例:**

```
public class Example {

    public static int multiply(int a, int b)
    {
        return a + b;
    }

    public static void main(String[] args)
    {
        int x = 2;
        int y = 5;

        // the variables x and y are arguments
        int sum = multiply(x, y);

        System.out.println("SUM IS: " + sum);
    }
}
```

**输出:**

```
SUM IS: 7

```