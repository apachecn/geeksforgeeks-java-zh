# 演示按值调用的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-按值演示调用/](https://www.geeksforgeeks.org/java-program-to-demonstrate-the-call-by-value/)

可以通过两种方式调用函数:[值调用](https://www.geeksforgeeks.org/difference-between-call-by-value-and-call-by-reference/)和[引用调用](https://www.geeksforgeeks.org/difference-between-call-by-value-and-call-by-reference/)。“按值调用”方法参数值被复制到另一个变量，然后复制的对象被传递，这就是为什么它被称为“按值传递”，而实际值不会改变

**用户案例:**在编程中调用方法，其中需要调用方法来使用其功能。在下面描述的条件下，调用方法或方法返回到调用它的代码时，可能会出现三种情况:

1.  它完成了方法中的所有语句
2.  它到达一个返回语句
3.  引发异常

> 记住:Java 总是按值调用的

**实现:**以数值调用的数字交换为例说明数值调用方法

*   **示例 1:** 通过在内存中创建一个称为临时变量的辅助空间来说明数字的交换

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program showcasing uses of call by value in examples

// Importing java input output classes
import java.io.*;

// Class
public class GFG {

    // Method to swap numbers
    static void swap(int a, int b)
    {

        // Creating a temporary variable in stack memory
        // and updating values in it.

        // Step 1
        int temp = a;
        // Step 2
        a = b;
        // Step 3
        b = temp;

        // This variables vanishes as scope is over
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Custom inputs/numbers to be swapped
        int x = 5;
        int y = 7;

        // Display message before swapping numbers
        System.out.println("before swaping x = " + x
                           + " and y = " + y);

        // Using above created method to swap numbers
        swap(x, y);

        // Display message after swapping numbers
        System.out.println("after swaping x = " + x
                           + " and y = " + y);
    }
}
```

**Output**

```java
before swaping x = 5 and y = 7
after swaping x = 5 and y = 7
```

输出说明:调用方法 swap(5，7)后，整数值 5 和 7 被复制到另一个变量中。所以*原值不变*。

*   **示例 2:** 说明了通过求和和删除数学计算来交换数字，而不创建任何辅助空间。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program showcasing uses of call by value in examples

// Importing java input output classes
import java.io.*;

// Class
class GFG {

    // Method to update value when called in main method
    static void change(int a)
    {
        // Random updation
        a = a + 50;
    }

    // Main driver method
    public static void main(String[] args)
    {

        // Random assassination
        int a = 30;

        // Printing value of variable
        // before calling  change() method
        System.out.println("before change a = " + a);

        // Calling above method in main() method
        change(a);

        // Printing value of variable
        // after calling  change() method
        System.out.println("after change a = " + a);
    }
}
```

**Output**

```java
before change a = 30
after change a = 30
```