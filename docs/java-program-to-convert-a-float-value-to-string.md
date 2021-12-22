# 将浮点值转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-a-float-value-to-string/](https://www.geeksforgeeks.org/java-program-to-convert-a-float-value-to-string/)

给定一个 Java 中的浮点值，任务是编写一个 Java 程序，将这个浮点值转换为字符串类型。

**示例:**

```java
Input: 1.0
Output: "1.0"

Input: 3.14
Output: "3.14"
```

**字符串–**Java 中的字符串是由一个字符数组在内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**浮点–**浮点数据类型是单精度 32 位 IEEE 754 浮点。它的价值范围是无限的。如果需要在大型浮点数数组中节省内存，建议使用浮点数(而不是双精度浮点数)。其默认值为 0.0F。

### 方法

在 Java 中，有许多方法可以将浮点值转换为字符串。这些是–

*   使用+运算符
*   使用 String.valueOf()方法
*   使用 Float.toString()方法

### **方法 1–使用+运算符**

一种方法是创建一个字符串变量，然后将浮点值附加到字符串变量。这将直接将浮点值转换为字符串，并将其添加到字符串变量中。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert float value to String value
class GFG {

    // Function to convert float value to String value
    public static String convertFloatToString(float floatValue)
    {
        // Convert float value to String value
        // using + operator method
        String stringValue = "" + floatValue;

        return (stringValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The float value
        float floatValue = 1f;

        // The expected string value
        String stringValue;

        // Convert float to string
        stringValue = convertFloatToString(floatValue);

        // Print the expected string value
        System.out.println(
            floatValue + " after converting into string = "
            + stringValue);
    }
}
```

**Output**

```java
1.0 after converting into string = 1.0
```

### **方法 2–使用 String.valueOf()方法**

最简单的方法是使用 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中[字符串类](https://www.geeksforgeeks.org/strings-in-java/)的 valueOf()方法。此方法接受要分析的浮点值，并从中返回字符串类型的值。

**语法:**

```java
String.valueOf(floatValue);
```

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert float value to String value
class GFG {

    // Function to convert float value to String value
    public static String
    convertFloatToString(float floatValue)
    {
        // Convert float value to String value
        // using valueOf() method
        return String.valueOf(floatValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The float value
        float floatValue = 1;

        // The expected string value
        String stringValue;

        // Convert float to string
        stringValue = convertFloatToString(floatValue);

        // Print the expected string value
        System.out.println(
            floatValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output**

```java
1.0 after converting into string = 1.0
```

### **方法 3–使用 Float.toString()方法**

Float.toString()方法也可用于将浮点值转换为字符串。toString()是 [**浮动类**](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) **的静态方法。**

**语法:**

```java
String str = Float.toString(val);
```

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert float value to String value
import java.util.*;
class GFG {

    // Function to convert float value to String value
    public static String
    convertFloatToString(float floatValue)
    {
        // Convert float value to String value
        // using valueOf() method
        return Float.toString(floatValue);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The float value
        float floatValue = 1;

        // The expected string value
        String stringValue;

        // Convert float to string
        stringValue = convertFloatToString(floatValue);

        // Print the expected string value
        System.out.println(
            floatValue
            + " after converting into string = "
            + stringValue);
    }
}
```

**Output**

```java
1.0 after converting into string = 1.0
```