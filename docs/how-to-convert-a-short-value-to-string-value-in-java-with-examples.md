# 如何在 Java 中将短值转换为字符串值，示例

> 原文:[https://www . geesforgeks . org/如何通过示例将 java 中的短值转换为字符串值/](https://www.geeksforgeeks.org/how-to-convert-a-short-value-to-string-value-in-java-with-examples/)

在 Java 中给定一个短值，任务是将这个短值转换成字符串类型。

**示例:**

```java
Input: 1
Output: "1"

Input: 3
Output: "3"

```

**方法 1:(使用+运算符)**
一种方法是创建一个字符串变量，然后将短值追加到字符串变量中。这将直接将短值转换为字符串，并将其添加到字符串变量中。

下面是上述方法的实现:

**例 1:**

```java
// Java Program to convert short value to String value

class GFG {

    // Function to convert short value to String value
    public static String
    convertShortToString(short shortValue)
    {

        // Convert short value to String value
        // using + operator method
        String stringValue = "" + shortValue;

        return (stringValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The short value
        short shortValue = 1;

        // The expected string value
        String stringValue;

        // Convert short to string
        stringValue
            = convertShortToString(shortValue);

        // Print the expected string value
        System.out.println(
            shortValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```java
1 after converting into string = 1

```

**方法二:(使用 String.valueOf()方法)**
最简单的方法就是使用 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中 [String 类](https://www.geeksforgeeks.org/strings-in-java/)的 **valueOf()方法**。此方法接受要分析的短值，并从中返回字符串类型的值。

**语法:**

```java
String.valueOf(shortValue);

```

下面是上述方法的实现:

**例 1:**

```java
// Java Program to convert short value to String value

class GFG {

    // Function to convert short value to String value
    public static String
    convertShortToString(short shortValue)
    {

        // Convert short value to String value
        // using valueOf() method
        return String.valueOf(shortValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The short value
        short shortValue = 1;

        // The expected string value
        String stringValue;

        // Convert short to string
        stringValue
            = convertShortToString(shortValue);

        // Print the expected string value
        System.out.println(
            shortValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```java
1 after converting into string = 1

```