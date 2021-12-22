# Java 程序演示一个有两个参数且没有返回类型的方法

> 原文:[https://www . geesforgeks . org/Java-program-to-installation-a-method-with-2-parameters-and-not-return-type/](https://www.geeksforgeeks.org/java-program-to-illustrate-a-method-with-2-parameters-and-without-return-type/)

不带返回类型的函数代表空函数。void 函数可能接受多个或零个参数，并且不返回任何内容。在这里，我们将定义一个方法，它接受 2 个参数并且不返回任何东西。

**语法:**

```java
public static void function(int a, int b)
```

**例:**

```java
public static voif fun1(String 1, String 2){
    // method execution code
};
```

**方法:**

1.  Take two inputs as two variables.
2.  Pass these inputs as parameters to the function.
3.  Displays the sum of the defined functions.

**代码:**

## Java

```java
// Java Program to Illustrate a Method
// with 2 Parameters and without Return Type
import java.util.*;
public class Main {
    public static void main(String args[])
    {
        int a = 4;
        int b = 5;

        // Calling the function with 2 parameters
        calc(a, b);
    }
    public static void calc(int x, int y)
    {
        int sum = x + y;
        // Displaying the sum
        System.out.print("Sum of two numbers is :" + sum);
    }
}
```

**输出**

```java
Sum of two numbers is :9
```