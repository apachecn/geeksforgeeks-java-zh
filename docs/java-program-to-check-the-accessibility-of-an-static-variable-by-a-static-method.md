# 通过静态方法检查静态变量可访问性的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-check-accessibility-a-static-variable-by-static-method/](https://www.geeksforgeeks.org/java-program-to-check-the-accessibility-of-an-static-variable-by-a-static-method/)

[**Static**](https://www.geeksforgeeks.org/static-keyword-java/) 关键字是 Java 中的非访问修饰符，主要用于内存管理。此静态关键字主要适用于以下情况:

1.  变量
2.  方法
3.  阻碍
4.  嵌套类

[静态变量](https://www.geeksforgeeks.org/static-variables-in-java-with-examples/)是一个声明为静态的变量，这意味着在类级别的所有对象之间创建并共享该变量的单个副本。**静态方法**是属于类的方法而不是类的对象，静态方法可以被调用而不需要创建类的实例。

> **注:**
> 
> *   静态变量在类中只获得一次内存
> *   静态方法可以访问静态数据成员，并可以更改其值。

现在，我们将通过干净的 java 程序进行简单的演示来讨论这两种情况，如下所示:

*   案例 1:静态变量对静态方法的可访问性
*   案例 2:静态方法对静态变量的可访问性

**案例 1:** 静态变量对静态方法的可访问性

将变量声明为静态，然后我们在静态方法中调用该变量，这样我们就可以将该变量作为输出。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate Accessibility of a static
// method/s by static variable/s

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Declaring static variable
    static int i = 10;

    // Main method
    public static void main(String[] args)
    {
        // Print and display the static variable
        System.out.println("Static Variable = " + i);
    }
}
```

**Output**

```java
Static Variable = 10
```

**情况 2:** 静态方法对静态变量的可访问性

将变量、数组和方法声明为静态，其中静态变量和静态数组由静态方法访问。调用静态方法时不创建类的实例。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate Accessibility of an static
// variable by static method

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Declaring and initializing variables
    // Making variables static
    static int i = 10;
    static int j = 20;

    // Declaring the static temporary array
    static int temp[] = { 2, 6, 3, 0, 1, 7 };

    // Method 1
    // Multiplication of array elements
    public static void multiply(int n)
    {
        for (int k = 0; k < n; k++) {
            // Multiplying each element of array with i=10
            temp[k] = temp[k] * i;
        }
    }

    // Method 2
    // To print an array
    public static void print_Array(int n)
    {
        // Display message
        System.out.print("\nArray = ");

        // Iteration using for loop to print complete array
        for (int m = 0; m < n; m++) {
            // Printing array element
            System.out.print(temp[m] + " ");
        }
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        // TODO Auto-generated method stub
        System.out.print("Static variable : " + i);

        // Length of static array temp[]
        int n = temp.length;

        // Calling the static multiply method
        multiply(n);

        // Calling the static Print_Array method
        print_Array(n);
    }
}
```

**Output**

```java
Static variable : 10
Array = 20 60 30 0 10 70 
```