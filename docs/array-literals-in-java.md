# Java 中的数组文字

> 原文:[https://www.geeksforgeeks.org/array-literals-in-java/](https://www.geeksforgeeks.org/array-literals-in-java/)

[字面上的](https://www.geeksforgeeks.org/literals-in-java/)不太可能是任何可以赋给变量的常数值。

插图:

```java
int x = 10; 
// Here 10 is a literal.
```

现在让我们坚持使用数组文字，就像原语和字符串文字一样，java 也允许我们使用数组文字。Java 定义了特殊的语法，允许我们在程序中初始化数组值。

**方法:**

创建数组文字有两种不同的方法。

1.  在创建数组对象时初始化数组元素。
2.  使用匿名数组

**方法 1:** 创建数组对象时数组元素的初始化。这是最常用的语法，只能在声明数组类型的变量时使用。

**语法:**

```java
int[] factorsOf24 = { 1, 2, 3, 4, 6, 12, 24 };
```

**实施:**

上面的语句创建了一个包含 7 个元素的 **int** 数据类型数组。在这里，我们:

*   在不使用**新**关键字的情况下创建了一个数组对象。
*   没有指定数组的类型。
*   没有明确指定数组对象的长度。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Array Literals by
// Initialization of array elements
// at the time of creating array object

// Importing required classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Initializing array elements at the time of
        // creating an array object
        int[] factorsOf24 = { 1, 2, 3, 4, 6, 12, 24 };

        // Iterating using for each loop
        for (int i : factorsOf24)

            // Print the elements
            System.out.print(i + " ");
    }
}
```

**Output**

```java
1 2 3 4 6 12 24 
```

> **注意:**这个方法有一个缺陷，因为这个数组文字语法只在将数组对象赋给变量时有效。如果您需要对数组值做一些事情，比如将它传递给一个方法，但是您将只使用该数组一次。在这种情况下，我们可以避免将其分配给变量，但是这种语法不允许我们这样做。

**方法 2:** 我们有另一种语法，允许我们使用匿名数组。匿名数组是不赋给任何变量的数组**(因此，它们没有名字)。**

**语法:**

```java
double volume = computeVolume(new int[] { 3, 4, 5 });
```

**实施:**

上面的语句调用了一个带有匿名数组的方法 **computeVolume** 。在这里，我们:

*   没有将数组存储在任何变量中。
*   使用**新的**关键字创建数组对象。
*   显式指定数组的类型。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Array Literals
// Using anonymous arrays

// Importing required classes
import java.io.*;

// Main class
public class GFG {

    // Method 1
    // To compute the volume
    public static double computeVolume(int[] dimensions)
    {

        int l = dimensions[0];
        int b = dimensions[1];
        int h = dimensions[2];

        // returning the volume
        return (l * b * h);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Passing an array object directly to a method
        // without storing it in a variable
        double volume
            = computeVolume(new int[] { 3, 4, 5 });

        // Print and display the volume
        System.out.print(volume);
    }
}
```

**Output**

```java
60.0
```