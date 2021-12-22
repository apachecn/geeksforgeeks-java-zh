# Java 一元运算符示例

> 原文:[https://www . geesforgeks . org/Java-一元运算符-带示例/](https://www.geeksforgeeks.org/java-unary-operator-with-examples/)

[**运算符**](https://www.geeksforgeeks.org/operators-in-java/) 构成了任何编程语言的基本构件。Java 也提供了许多类型的运算符，可以根据需要使用它们来执行各种计算和功能，包括逻辑、算术、关系等。它们根据提供的功能进行分类。这里有几种类型:

1.  arithmetic operator
2.  Unary operator
3.  assigning operator
4.  relational operator
5.  logical operator
6.  ternary operator
7.  Bitwise operator
8.  Shift operator

## **Java 中的一元运算符**

Java 一元运算符是只需要一个操作数来执行任何操作的类型，如递增、递减、求反等。它由对单个操作数进行运算的各种算术、逻辑和其他运算符组成。让我们详细看看各种一元运算符，看看它们是如何操作的。

### **运算符 1:** 一元减号(-)

该运算符可用于将负值转换为正值。

**语法:**

```java
~(operand)
```

**插图:**

```java
a = -10
```

**示例:**

## Java

```java
// Java Program to Illustrate Unary - Operator

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring a custom variable
        int n1 = 20;

        // Printing the above variable
        System.out.println("Number = " + n1);

        // Performing unary operation
        n1 = -n1;

        // Printing the above result number
        // after unary operation
        System.out.println("Result = " + n1);
    }
}
```

**输出**

```java
Number = 20
Result = -20
```

### **运算符 2:** “非”运算符(！)

这用于将真转换为假，反之亦然。基本上，它颠倒了操作数的逻辑状态。

**语法:**

```java
!(operand)
```

**插图:**

```java
cond = !true;
*// cond < false*
```

**例:**

## 爪哇

```java
// Java Program to Illustrate Unary NOT Operator

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing variables
        boolean cond = true;
        int a = 10, b = 1;

        // Displaying values stored in above variables
        System.out.println("Cond is: " + cond);
        System.out.println("Var1 = " + a);
        System.out.println("Var2 = " + b);

        // Displaying values stored in above variables
        // after applying unary NOT operator
        System.out.println("Now cond is: " + !cond);
        System.out.println("!(a < b) = " + !(a < b));
        System.out.println("!(a > b) = " + !(a > b));
    }
}
```

**输出:**

```java
Cond is: true
Var1 = 10
Var2 = 1
Now cond is: false
!(a < b) = true
!(a > b) = false
```