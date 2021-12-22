# 如何在 Java 中将字节值转换为字符串值，示例

> 原文:[https://www . geesforgeks . org/如何通过示例将字节值转换为 java 字符串值/](https://www.geeksforgeeks.org/how-to-convert-a-byte-value-to-string-value-in-java-with-examples/)

在 Java 中给定一个字节值，任务是将这个字节值转换成字符串类型。

**示例:**

```
Input: 1
Output: "1"

Input: 3
Output: "3"

```

**方法 1:(使用+运算符)**
一种方法是创建一个字符串变量，然后在+运算符的帮助下将字节值追加到字符串变量中。这将直接将字节值转换为字符串，并将其添加到字符串变量中。

下面是上述方法的实现:

**例 1:**

```
// Java Program to convert
// byte value to String value

class GFG {

    // Function to convert
    // byte value to String value
    public static String
    convertByteToString(byte byteValue)
    {

        // Convert byte value to String value
        // using + operator method
        String stringValue = "" + byteValue;

        return (stringValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The byte value
        byte byteValue = 1;

        // The expected string value
        String stringValue;

        // Convert byte to string
        stringValue
            = convertByteToString(byteValue);

        // Print the expected string value
        System.out.println(
            byteValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```
1 after converting into string = 1

```

**方法二:(使用 String.valueOf()方法)**
最简单的方法就是在 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中使用 [String 类](https://www.geeksforgeeks.org/strings-in-java/)的 valueOf()方法。此方法获取要分析的字节值，并从中返回字符串类型的值。

**语法:**

```
String.valueOf(byteValue);

```

下面是上述方法的实现:

**例 1:**

```
// Java Program to convert
// byte value to String value

class GFG {

    // Function to convert
    // byte value to String value
    public static String
    convertByteToString(byte byteValue)
    {

        // Convert byte value to String value
        // using valueOf() method
        return String.valueOf(byteValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The byte value
        byte byteValue = 1;

        // The expected string value
        String stringValue;

        // Convert byte to string
        stringValue
            = convertByteToString(byteValue);

        // Print the expected string value
        System.out.println(
            byteValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```
1 after converting into string = 1

```