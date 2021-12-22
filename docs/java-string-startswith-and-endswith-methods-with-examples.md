# Java 字符串 startsWith()和 endsWith()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-starts with-and-ends with-methods-with-examples/](https://www.geeksforgeeks.org/java-string-startswith-and-endswith-methods-with-examples/)

Java 中的 String 类是一种不可变的非原语数据类型，用于存储序列的字符。字符串是非基本数据类型，因为在字符串变量的初始化过程中，它引用了一个对象，该对象包含可以执行几种不同类型操作的方法，但是根据基本数据类型的定义，它们不被视为对象，而是将数据存储在堆栈内存中。在本文中，我们将讨论 java 中 String 类的 endWith()方法和 startsWith()方法。

让我们分别讨论这两种方法:java 中的

1.  enWith()方法
2.  startwitch_)启动开关

**方法 1:** [endsWith()方法](https://www.geeksforgeeks.org/java-string-endswith-examples/)

字符串类的这个方法检查给定的字符串是否以指定的字符串后缀结尾。

**语法:**

```
endsWith(String suffix)     
```

**参数:**该方法取一个字符串类型的参数..

**返回类型:**该方法返回一个布尔值 true 或 false。即字符串是否以指定的后缀结尾。

**示例:**

## Java

```
// Java Program to illustrate endWith() Method

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Given String
        String first = "Geeks for Geeks";

        // Suffix to be matched
        String suffix = "kse";

        // Given String does not end with
        // the above suffix hence return false
        System.out.println(first.endsWith(suffix));

        // Changing the suffix say
        // it be customly 's'
        suffix = "s";

        // Given String ends with the given suffix  hence
        // returns true
        System.out.println(first.endsWith(suffix));
    }
}
```

**输出**

```
false
true
```

**方法 2:**T2【starts with()方法

字符串类的这个方法检查给定的字符串是否以指定的字符串前缀开始。

**语法:**

```
startsWith(String prefix)     
```

**参数:**该方法取一个字符串类型的参数..

**返回类型:**该方法返回一个布尔值 true 或 false。即字符串是否以指定的前缀结尾。

**示例:**

## Java

```
// Java Program to illustrate startWith() Method

// Importing required classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Given String
        String first = "Geeks for Geeks";

        // Prefix to be matched
        String prefix = "se";

        // Given String does not start with the above prefix
        // hence return false
        System.out.println(first.startsWith(prefix));

        // Changing the prefix
        prefix = "Gee";

        // Given String starts with the given prefix hence
        // returns true
        System.out.println(first.startsWith(prefix));
    }
}
```

**输出**

```
false
true
```