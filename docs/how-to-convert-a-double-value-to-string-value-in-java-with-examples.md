# 如何在 Java 中将双精度值转换为字符串值，示例

> 原文:[https://www . geesforgeks . org/如何用示例将双值转换为字符串值/Java/](https://www.geeksforgeeks.org/how-to-convert-a-double-value-to-string-value-in-java-with-examples/)

在 Java 中给定一个 double 值，任务是将这个 Double 值转换成字符串类型。

**示例:**

```java
Input: 1.0
Output: "1.0"

Input: 3.14
Output: "3.14"

```

**方法 1:(使用+运算符)**
一种方法是创建一个字符串变量，然后将双精度值追加到字符串变量中。这将直接将双精度值转换为字符串，并将其添加到字符串变量中。

下面是上述方法的实现:

**例 1:**

```java
// Java Program to convert double value to String value

class GFG {

    // Function to convert double value to String value
    public static String
    convertDoubleToString(double doubleValue)
    {

        // Convert double value to String value
        // using + operator method
        String stringValue = "" + doubleValue;

        return (stringValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The double value
        double doubleValue = 1;

        // The expected string value
        String stringValue;

        // Convert double to string
        stringValue
            = convertDoubleToString(doubleValue);

        // Print the expected string value
        System.out.println(
            doubleValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```java
1.0 after converting into string = 1.0

```

**方法二:(使用 String.valueOf()方法)**
最简单的方法就是在 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中使用 [String 类](https://www.geeksforgeeks.org/strings-in-java/)的 valueOf()方法。此方法接受要分析的双精度值，并从中返回字符串类型的值。

**语法:**

```java
String.valueOf(doubleValue);

```

下面是上述方法的实现:

**例 1:**

```java
// Java Program to convert double value to String value

class GFG {

    // Function to convert double value to String value
    public static String
    convertDoubleToString(double doubleValue)
    {

        // Convert double value to String value
        // using valueOf() method
        return String.valueOf(doubleValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The double value
        double doubleValue = 1;

        // The expected string value
        String stringValue;

        // Convert double to string
        stringValue
            = convertDoubleToString(doubleValue);

        // Print the expected string value
        System.out.println(
            doubleValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output:**

```java
1.0 after converting into string = 1.0

```