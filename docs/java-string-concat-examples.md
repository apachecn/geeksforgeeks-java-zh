# Java String concat()带示例

> 原文:[https://www.geeksforgeeks.org/java-string-concat-examples/](https://www.geeksforgeeks.org/java-string-concat-examples/)

[Java 字符串](https://www.geeksforgeeks.org/string-class-in-java/) *concat()方法*将一个字符串连接到另一个字符串的末尾。此方法返回一个字符串，该字符串的值被传递到方法中，并附加到字符串的末尾。考虑下图:

**插图:**

```
Input:  String 1   : abc
        String 2   : def
        String n-1 : ...
        String n   : xyz
Output: abcdef...xyz        
```

**语法:**

```
public String concat(String anostr)   
```

**参数:**要连接在另一个字符串末尾的字符串

**返回:**串联(组合)字符串

**示例:**

## Java

```
// Java program to Illustrate Working of concat() method
// with Strings
// By explicitly assigning result

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Custom input string 1
        String s = "Hello ";

        // Custom input string 2
        s = s.concat("World");

        // Explicitly assigning result by
        // Combining(adding, concatenating strings)
        // using concat() method

        // Print and display combined string
        System.out.println(s);
    }
}
```

**输出**

```
Hello World
```

**例 2:**

## Java

```
// Java program to Illustrate Working of concat() method
// in strings where we are sequentially
// adding multiple strings as we need

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Custom string 1
        String str1 = "Computer-";

        // Custom string 2
        String str2 = "-Science";

        // Combining above strings by
        // passing one string as an argument
        String str3 = str1.concat(str2);

        // Print and display temporary combined string
        System.out.println(str3);

        String str4 = "-Portal";
        String str5 = str3.concat(str4);
        System.out.println(str5);
    }
}
```

**输出**

```
Computer--Science
Computer--Science-Portal
```

从代码中可以看出，我们可以多次连接字符串，绕过旧的字符串，用新的字符串作为参数进行污染，并将结果字符串存储在字符串数据类型中。