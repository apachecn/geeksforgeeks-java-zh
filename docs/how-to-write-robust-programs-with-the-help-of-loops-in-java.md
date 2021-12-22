# 如何借助 Java 中的循环编写健壮的程序？

> 原文:[https://www . geesforgeks . org/如何借助 java 中的循环编写健壮的程序/](https://www.geeksforgeeks.org/how-to-write-robust-programs-with-the-help-of-loops-in-java/)

这里我们将讨论如何借助循环来编写有效的代码。人们普遍认为，使用循环的方法被视为解决问题陈述的幼稚方法。但是，这里仍然有很大的即兴创作空间。所以基本上，循环语句允许我们多次执行一条语句或一组语句。除此之外，我们还可以根据我们的需求操纵它的执行，并编写健壮的代码。

假设你想找到一个圆的面积和周长。新手程序员的一般方法是检查半径是否大于零。如果不是，则打印输入非零正数。现在，这里有什么缺陷？如果用户多次输入小于或等于零的数字，那么我们需要一次又一次地编译我们的代码，因为程序将打印输入非零正数并完成它的执行。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Simply Get the Area of Shapes
// Without considering robustness into play

// Importing Scanner class to
// read input
import java.util.Scanner;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of Scanner class to
        // take input
        Scanner s = new Scanner(System.in);
        System.out.println("Enter Radius::");
        double radius = s.nextDouble();
        double perimeter;
        double area;

        // If radius is negative
        if (radius <= 0) {

            System.out.println(
                "please enter non zero positive number ");
        }

        // Radius is positive
        else {

            // Compute area and perimeter
            perimeter = 2 * Math.PI * radius;
            area = Math.PI * radius * radius;

            // Print and display area and parameter
            System.out.println("Perimeter:: " + perimeter);
            System.out.println("Area:: " + area);
        }
    }
}
```

**输出:**

```
C:\Users\USER\Desktop\Network Java>javac GFG.java
C:\Users\USER\Desktop\Network Java>java GFG
Enter Radius::
-5
please enter non zero positive number
//Execution Finished
```

```
C:\Users\USER\Desktop\Network Java>javac GFG.java
C:\Users\USER\Desktop\Network Java>java GFG
Enter Radius::
0
please enter non zero positive number
//Execution Finished
```

输出解释:

在上面的例子中，我们看到如果用户输入任何非零和负整数，那么我们需要一次又一次地编译和运行程序。使用 while 循环可以避免这种尴尬的情况。使用循环，我们可以根据我们的需求操纵它的执行，并编写健康的代码。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate Robustness In a Program
// Using Loops

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {
        // Custom input - Radius of a circle
        double radius = 50;

        // Reading input
        BufferedReader br = new BufferedReader(
            new InputStreamReader(System.in));

        // Asking from user to enter radius
        System.out.println("Enter Radius::");

        // 1st.This while loop will run since
        // 50>Integer.MIN_VALUE
        while (radius > Integer.MIN_VALUE) {

            // 2nd.It's time to read the buffer
            radius = Double.parseDouble(br.readLine()); //**

            // 3rd.If radius>0 give result and break the
            // loop.
            if (radius > 0) {
                double Perimeter = 2 * Math.PI * radius;
                double Area = Math.PI * Math.pow(radius, 2);
                System.out.println("Perimeter:: "
                                   + Perimeter);
                System.out.println("Area:: " + Area);
                break;
            }

            // 4th.If radius=-100(say) then print the
            // following
            System.out.println(
                "please enter non zero positive number");
            System.out.println("Enter Radius::");

            // 5th.As -100>Integer.MIN_VALUE the loop will
            // run again.
        }
    }
}
```

**输出:**

```
C:\Users\USER\Desktop\Network Java>javac GFG.java
C:\Users\USER\Desktop\Network Java>java GFG
Enter Radius::
-10
please enter non zero positive number
Enter Radius::
0
please enter non zero positive number
Enter Radius::
3
Perimeter:: 18.84955592153876
Area:: 28.274333882308138
//Execution Finished
```

> **注意:**在上面的程序中，我们看到如果我们读取缓冲区一次，那么它将不再存储任何东西。如果我们试着再读一遍，它会要求输入。