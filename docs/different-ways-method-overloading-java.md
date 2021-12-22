# Java 中方法重载的不同方式

> 原文:[https://www . geesforgeks . org/different-way-method-overloading-Java/](https://www.geeksforgeeks.org/different-ways-method-overloading-java/)

[Java 中的方法重载](https://www.geeksforgeeks.org/overloading-in-java/)是基于作为参数传递给方法的参数的数量和类型。我们不能定义多个具有相同名称、顺序和参数类型的方法。这将是一个编译器错误。编译器在区分重载方法时不考虑返回类型。但是不能用相同的签名和不同的返回类型声明两个方法。它将引发编译时错误。如果两个方法具有相同的参数类型，但是返回类型不同，那么这是不可能的。

Java 可以区分**不同方法签名**的方法。即这些方法可以具有相同的名称，但是在同一类中具有不同的参数列表(即参数的数量、参数的顺序和参数的数据类型)。

极客们，现在你们知道为什么我们需要方法重载了吧？

如果我们需要以不同的方式进行某种操作，即针对不同的输入。在下面描述的例子中，我们对不同的输入进行加法运算。很难为一个动作找到很多有意义的名字。

### **超载方式**

方法重载可以通过改变:

1.  The number of parameters of the two methods.
2.  The data type of the method.
3.  The order of the parameters.

让我们举几个例子来说明重载方法时的每一种方法。它们如下:

**方法 1:** 通过改变参数数量**。**

## Java

```java
// Java Program to Illustrate Method Overloading
// By Changing the Number of Parameters

// Importing required classes
import java.io.*;

// Class 1
// Helper class
class Addition {

    // Method 1
    // Adding two integer values
    public int add(int a, int b)
    {

        int sum = a + b;
        return sum;
    }

    // Method 2
    // Adding three integer values
    public int add(int a, int b, int c)
    {

        int sum = a + b + c;
        return sum;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of above class inside main()
        // method
        Addition ob = new Addition();

        // Calling method to add 3 numbers
        int sum1 = ob.add(1, 2);

        // Printing sum of 2 numbers
        System.out.println("sum of the two integer value :"
                           + sum1);

        // Calling method to add 3 numbers
        int sum2 = ob.add(1, 2, 3);

        // Printing sum of 3 numbers
        System.out.println(
            "sum of the three integer value :" + sum2);
    }
}
```

**输出**

```java
sum of the two integer value :3
sum of the three integer value :6

```

**方法二:**通过改变参数

T5】JavaT7

```java
// Java Program to Illustrate Method Overloading
// By Changing Data Types of the Parameters

// Importing required classes
import java.io.*;

// Class 1
// Helper class
class Addition {

    // Adding three integer values
    public int add(int a, int b, int c)
    {

        int sum = a + b + c;
        return sum;
    }

    // adding three double values.
    public double add(double a, double b, double c)
    {

        double sum = a + b + c;
        return sum;
    }
}

class GFG {
    public static void main(String[] args)
    {

        Addition ob = new Addition();

        int sum2 = ob.add(1, 2, 3);
        System.out.println(
            "sum of the three integer value :" + sum2);
        double sum3 = ob.add(1.0, 2.0, 3.0);
        System.out.println("sum of the three double value :"
                           + sum3);
    }
}
```

T8T10**输出**T1

**方法 3:** 通过改变参数的顺序

## Java

```java
// Java Program to Illustrate Method Overloading
// By changing the Order of the Parameters

// Importing required classes
import java.io.*;

// Class 1
// Helper class
class Geek {

    // Method 1
    public void geekIdentity(String name, int id)
    {

        // Printing name and id o person
        System.out.println("geekName :" + name + " "
                           + "Id :" + id);
    }

    // Method 2
    public void geekIdentity(int id, String name)
    {

        // Again printing name and id o person
        System.out.println("Id :" + id + " "
                           + "geekName :" + name);
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of above class
        Geek geek = new Geek();

        // Passing name and id
        // Note: Reverssing order
        geek.geekIdentity("Mohit", 1);
        geek.geekIdentity(2, "shubham");
    }
}
```

**输出**

```java
geekName :Mohit Id :1
geekName :shubham Id :2
```