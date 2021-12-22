# Java 中的 Getter 和 Setter

> 原文:[https://www.geeksforgeeks.org/getter-and-setter-in-java/](https://www.geeksforgeeks.org/getter-and-setter-in-java/)

Getter 和 Setter 是用于保护数据和使代码更加安全的方法。Getter 返回值(访问器)，它返回 int、String、double、float 等数据类型的值。为了程序的方便，getter 以单词“get”开头，后跟变量名。

而 Setter 设置或更新值(变异器)。它为类的程序中使用的任何变量设置值。并以单词“set”开头，后跟变量名。Getter 和 Setter 使程序员能够方便地设置和获取特定数据类型的值。在 getter 和 setter 中，变量的第一个字母都应该是大写。

**例 1**

## 爪哇

```java
// Java Program to Illustrate Getter and Setter

// Importing input output classes
import java.io.*;

// Class 1
// Helper class
class GetSet {

    // Member variable of this class
    private String name;

    // Method 1 - Getter
    public String getName() { return name; }

    // Method 2 - Setter
    public void setName(String N)
    {

        // This keyword refers to current instance itself
        this.name = N;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of class 1 in main() method
        GetSet obj = new GetSet();

        // Setting the name by calling setter method
        obj.setName("Geeks for Geeks");
        // Getting the name by calling geter method
        System.out.println(obj.getName());
    }
}
```

**输出**

```java
Geeks for Geeks

```