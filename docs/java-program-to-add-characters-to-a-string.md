# 向字符串添加字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-将字符添加到字符串/](https://www.geeksforgeeks.org/java-program-to-add-characters-to-a-string/)

我们将讨论如何在 java 中将字符添加到字符串的特定位置。如图所示，我们试图做的事情可以解释如下:

**插图:**

```java
Input: 
Input custom string = Hello
Output: 
--> String to be added 'Geeks'
    --> If end position, Output: HelloGeeks
    --> If in beginning, Output: GeeksHello
    --> If at sat 3rd index, Output: HelGeekslo 
```

**方法:**这可以使用多种方法来完成，其中常用的方法如下:

让我们详细讨论上面列出的所有三种方法，以便对它们有一个公平的理解

**方法 1:** [使用+运算符](https://www.geeksforgeeks.org/operators-in-java/)

**1.1** 末

**示例:**可以使用“+”运算符在字符串的开头添加字符。

## Java

```java
// Java Program to Add Characters to a String
// At the End

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Input character and string
        char a = 's';
        String str = "GeeksforGeek";

        // Inserting at the end
        String str2 = str + a;

        // Print and display the above string
        System.out.println(str2);
    }
}
```

**输出**

```java
GeeksforGeeks
```

**1.2** 开头

**示例:**可以使用“+”运算符在字符串的开头添加字符。

## Java

```java
// Java Program to Add Characters to a String
// At the Beginning

// Importing input output classes
import java.io.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Input character and string
        char a = 'G';
        String str = "eeksforGeeks";

        // Inserting at the beginning
        String str2 = a + str;

        // Print and display the above string
        System.out.println(str2);
    }
}
```

**输出**

```java
GeeksforGeeks
```

**方法二:** [使用 insert()方法的 StringBuffer 类**T5】**](https://www.geeksforgeeks.org/stringbuffer-insert-java/)

**StringBuffer 是 String 的对等类，它提供了字符串的大部分功能。该字符串表示固定长度、不可变的字符序列，而 StringBuffer 表示可增长和可写的字符序列。StringBuffer 可以在中间插入字符和子字符串，也可以附加到末尾。它会自动增长，为这种添加腾出空间，并且通常会预分配比实际需要更多的字符，以留出增长空间。可以使用 StringBuffer 类方法，即 insert()方法，在给定位置向 String 添加字符。此方法在 StringBuffer 中的给定位置插入给定数据类型的字符串表示形式。**

****语法:****

```java
 str.insert(int position,  char x);
 str.insert(int position,  boolean x);
 str.insert(int position,  char[] x);
 str.insert(int position, float x);
 str.insert(int position, double x);
 str.insert(int position, long x);
 str.insert(int position, int x);

**position** is the index in string where
we need to insert.
```

****返回类型:**对此对象的引用。**

****示例****

## **Java**

```java
// Java Program to Add Characters to a String
// Using StringBuffer class insert() method

// Main class
// AddCharacterToStringAnyPosition
public class GFG {

    // Method 1
    // To add character to string
    public static String addCharToString(String str, char c,
                                         int pos)
    {

        // Creating an object of StringBuffer class
        StringBuffer stringBuffer = new StringBuffer(str);

        // insert() method where position of character to be
        // inserted is specified as in arguments
        stringBuffer.insert(pos, c);

        // Return the updated string
        // Concatenated string
        return stringBuffer.toString();
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Input string and character
        String blogName = "GeeksorGeeks";
        char two = 'f';

        // Calling the method 1 to
        // add character to a string

        // Custom string, character and position passed
        String cblogName
            = addCharToString(blogName, two, 5);

        // Print and display th above string
        System.out.println(cblogName);
    }
}
```

****输出**

```java
GeeksforGeeks
```** 

****方法 3:** [使用子串()方法](https://www.geeksforgeeks.org/substring-in-java/)**

**也可以使用 string 的 substring 方法将字符添加到给定位置的 String 中。这个方法有两个变体，它返回一个新的字符串，它是一个字符串的子字符串，其中子字符串从指定索引处的一个字符开始，一直延伸到字符串的末尾。**

****语法:****

```java
public String substring(int begIndex)
```

****参数:**起始指数，含。**

****返回值:**指定的子字符串。**

****示例****

## **Java**

```java
// Java Program to Add Characters to a String
// Using substring() method

// Main class
// AddCharacterToStringAnyPosition
public class GFG {

    // Method 1
    // To add character to a string
    public static String
    addCharToStringUsingSubString(String str, char c,
                                  int pos)
    {
        return str.substring(0, pos) + c
            + str.substring(pos);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom input character and string
        String blogName = "GeeksorGeeks";
        char two = 'f';

        // Calling the Method 1 to
        // To add character to a string

        // Custom arguments
        String cblogName = addCharToStringUsingSubString(
            blogName, two, 5);

        // Print and display the above string on console
        System.out.println(cblogName);
    }
}
```

****输出**

```java
GeeksforGeeks
```**