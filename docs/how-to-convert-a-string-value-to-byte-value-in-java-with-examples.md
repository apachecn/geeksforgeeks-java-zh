# 如何在 Java 中将字符串值转换为字节值，示例

> 原文:[https://www . geesforgeks . org/如何通过示例将字符串值转换为 java 中的字节值/](https://www.geeksforgeeks.org/how-to-convert-a-string-value-to-byte-value-in-java-with-examples/)

给定一个 Java 中的字符串“ **str** ，任务是将这个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)转换为[字节](https://www.geeksforgeeks.org/java-lang-byte-class-java/)类型。

**示例:**

```java
Input: str = "1"
Output: 1

Input: str = "3"
Output: 3

```

**方法 1:(天真方法)**
一种方法是遍历字符串，将数字一个接一个地添加到字节类型中。这种方法不是一种有效的方法。

**方法 2:(使用 Byte.parseByte()方法)**
最简单的方法是使用 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **parseByte()方法**。此方法接受要分析的字符串，并从中返回字节类型。如果不可转换，此方法将引发错误。

**语法:**

```java
Byte.parseByte(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```java
// Java Program to convert string to byte

class GFG {

    // Function to convert String to Byte
    public static byte convertStringToByte(String str)
    {

        // Convert string to byte
        // using parseByte() method
        return Byte.parseByte(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1";

        // The expected byte value
        byte byteValue;

        // Convert string to byte
        byteValue = convertStringToByte(stringValue);

        // Print the expected byte value
        System.out.println(
            stringValue
            + " after converting into byte = "
            + byteValue);
    }
}
```

**Output:**

```java
1 after converting into byte = 1

```

**方法 3:(使用 Byte.valueOf()方法)**
[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **valueOf()方法**将数据从其内部形式转换为人类可读形式。

**语法:**

```java
Byte.valueOf(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```java
// Java Program to convert string to byte

class GFG {

    // Function to convert String to Byte
    public static byte convertStringToByte(String str)
    {

        // Convert string to byte
        // using valueOf() method
        return Byte.valueOf(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1";

        // The expected byte value
        byte byteValue;

        // Convert string to byte
        byteValue = convertStringToByte(stringValue);

        // Print the expected byte value
        System.out.println(
            stringValue
            + " after converting into byte = "
            + byteValue);
    }
}
```

**Output:**

```java
1 after converting into byte = 1

```