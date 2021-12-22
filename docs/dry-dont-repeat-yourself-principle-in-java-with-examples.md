# Java 中 DRY(不要重复自己)原理举例

> 原文:[https://www . geesforgeks . org/dry-不要重复自己-java 中的原则-示例/](https://www.geeksforgeeks.org/dry-dont-repeat-yourself-principle-in-java-with-examples/)

DRY 只是一种方法，或者我们可以对程序员说一种不同的感知。代表不要重复自己。在 Java 中，这意味着不要重复编写相同的代码。假设你在程序的许多地方都有相同的代码，那么这就是所谓的 DRY，你在不同的地方重复相同的代码。因此，通过将方法放置在所有重复代码的位置，并在一个方法中定义代码，使用 DRY 概念来获得解决方案。所以通过调用方法，我们将达到 DRY 的原则。

**应用:**

*   在线营销应用
*   教育
*   金融应用

插图:

> 考虑一下大学生系统的情况。该学院包括许多系。所以每个系都有不同的人，但是学院的名字是一样的。所以不需要通过编写显示学院名的代码来为每个系指定学院名。

**实施:**无干法

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program without DRY approach

// Main class
public class GFG {

    // Method 1
    // For cse department
    public void CSE()
    {
        System.out.println("This is computer science");
    }

    // Method 2
    // For cse dept. college
    public void college()
    {
        System.out.println("IIT - Madras");
    }
    // Method 3
    // ece dept method
    public void ECE()
    {
        System.out.println("This is electronics");
    }

    // Method 4
    // For ece dept college 1
    public void college1()
    {
        System.out.println("IIT - Madras");
    }
    // Method 5
    // For IT dept
    public void IT()
    {
        System.out.println(
            "This is Information Technology");
    }

    // Method 6
    // For IT dept college 2
    public void college2()
    {
        System.out.println("IIT - Madras");
    }

    // Method 7
    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of class in main() method
        GFG s = new GFG();

        // Calling above methods one by one
        // as created above
        s.CSE();
        s.college();
        s.ECE();
        s.college1();
        s.IT();
        s.college2();
    }
}
```

**Output**

```
This is computer science
IIT - Madras
This is electronics
IIT - Madras
This is Information Technology
IIT - Madras

```

**实现:**应用 DRY 原理

*   这里我们只创建一个名为 college 的方法，然后在所有部门中调用该方法。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program with Use of DRY Concept

// Importing input output classes
import java.util.*;

// Main class
public class GFG {

    // Method 1
    // For cse department
    public void CSE()
    {

        // Print statement
        System.out.println("This is computer science");

        // Calling method
        college();
    }

    // Method 2
    // For ece dept method
    public void ECE()
    {
        System.out.println("This is electronics");

        // Calling method
        college();
    }

    // Method 3
    // For IT dept
    public void IT()
    {

        // Print statement
        System.out.println(
            "This is Information Technology");

        // Callling method
        college();
    }

    // Method 4
    // For college dept
    public void college()
    {

        // Print statement
        System.out.println("IIT - Madras");
    }

    // Method 5
    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of class in main() method
        GFG s = new GFG();

        // Calling the methods one by one
        // as created above
        s.CSE();
        s.ECE();
        s.IT();
    }
}
```

**Output**

```
This is computer science
IIT - Madras
This is electronics
IIT - Madras
This is Information Technology
IIT - Madras

```

**实现:**申请了**T3】DRY app**r**appear 后，一家银行相关人员的银行名称**

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program with Use of DRY Concept

// Importing input output classes
import java.util.*;

// Main class
public class GFG {

    // Method 1
    // For person1
    public void person1()
    {

        // Print statement
        System.out.println("sravan");

        // Calling Method 3
        bank();
    }

    // Method 2
    // For person 2
    public void person2()
    {

        // Print statement
        System.out.println("ramya");

        // Calling method 3
        bank();
    }

    // Method 3
    // For bank
    public void bank()
    {

        // Print statement
        System.out.println("SBI");
    }

    // Method 4
    // Main driver method
    public static void main(String[] args)
    {

        // Creating objectof class in main() method
        GFG s = new GFG();

        // Calling the methods one by one
        s.person1();
        s.person2();
    }
}
```

**Output**

```
sravan
SBI
ramya
SBI

```