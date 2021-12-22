# Java 字符串格式()方法示例

> 原文:[https://www . geesforgeks . org/Java-string-format-method-with-examples/](https://www.geeksforgeeks.org/java-string-format-method-with-examples/)

在 java 中， ***String format()方法*** 使用给定的**区域设置**、指定的**格式字符串**和**参数**返回格式化字符串。我们可以使用这个方法连接字符串，同时，我们可以格式化输出的连接字符串。

**语法:**有两种类型的**字符串格式()**方法

```
public static String format(Locale loc, String form, Object... args)
```

```
public static String format(String form, Object... args)
```

**参数:**

*   要应用于 format()方法的区域设置值
*   输出字符串的格式。
*   指定格式字符串参数数量的参数。它可能为零或更多。

**返回类型:**格式化字符串。

**异常抛出:**

*   [空指针异常:](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) 如果格式为空。
*   [illegalformatException:](https://www.geeksforgeeks.org/console-readline-method-in-java-with-examples/)**如果指定的格式不合法或参数不足。**

****例 1:****

## **Java 语言（一种计算机语言，尤用于创建网站）**

```
// Java program to demonstrate
// working of format() method

// Main class
class GFG {

    // MAin driver method
    public static void main(String args[])
    {
        // Custom input string to be formatted
        String str = "GeeksforGeeks";

        // Concatenation of two strings
        String s = String.format("My Company name is %s", str);

        // Output is given upto 8 decimal places
        String str2 = String.format("My answer is %.8f", 47.65734);

        // Here answer is supposed to be %15.8f" and
        // "47.65734000" there are 15 spaces
        String str3 = String.format("My answer is %15.8f",
                                    47.65734);

        // Print and display strings
        System.out.println(s);
        System.out.println(str2);
        System.out.println(str3);
    }
}
```

****Output**

```
My Company name is GeeksforGeeks
My answer is 47.65734000
My answer is     47.65734000
```** 

****例 2:****

## **Java 语言（一种计算机语言，尤用于创建网站）**

```
// Java program to demonstrate Concatenation of Arguments
// to the string using format() method

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Custom input string to be formatted
        String str1 = "GFG";
        String str2 = "GeeksforGeeks";

        // %1$ represents first argument
        // %2$ second argument
        String str = String.format(
            "My Company name"
                + " is: %1$s, %1$s and %2$s",
            str1, str2);

        // Print and display the formatted string
        System.out.println(str);
    }
}
```

****Output:** 

```
My Company name is: GFG, GFG and GeeksforGeeks
```** 

****例 3:****

## **Java 语言（一种计算机语言，尤用于创建网站）**

```
// Java program to Illustrate Left Padding
// using format() method

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Custom integer number
        int num = 7044;

        // Output is 3 zero's("000") + "7044",
        // in total 7 digits
        String str = String.format("%07d", num);

        // Print and display the formatted string
        System.out.println(str);
    }
}
```

****Output:** 

```
0007044
```**