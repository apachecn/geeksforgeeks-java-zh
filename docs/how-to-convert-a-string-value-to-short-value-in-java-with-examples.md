# 如何在 Java 中将字符串值转换为短值，示例

> 原文:[https://www . geesforgeks . org/如何通过示例将字符串值转换为 java 短值/](https://www.geeksforgeeks.org/how-to-convert-a-string-value-to-short-value-in-java-with-examples/)

在 Java 中给定一个字符串“ **str** ，任务是将这个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)转换为[短](https://www.geeksforgeeks.org/java-lang-short-class-java/)类型。

**示例:**

```
Input: str = "1"
Output: 1

Input: str = "3"
Output: 3

```

**方法 1:(天真法)**
一种方法是遍历字符串，将数字一个接一个地添加到短类型中。这种方法不是一种有效的方法。

**方法二:(使用 Short.parseShort()方法)**
最简单的方法就是使用 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中[短类](https://www.geeksforgeeks.org/java-lang-short-class-java/)的 **parseShort()方法**。此方法接受要分析的字符串，并从中返回短类型。如果不可转换，此方法将引发错误。

**语法:**

```
Short.parseShort(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```
// Java Program to convert string to short

class GFG {

    // Function to convert String to Short
    public static short convertStringToShort(String str)
    {

        // Convert string to short
        // using parseShort() method
        return Short.parseShort(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1";

        // The expected short value
        short shortValue;

        // Convert string to short
        shortValue = convertStringToShort(stringValue);

        // Print the expected short value
        System.out.println(
            stringValue
            + " after converting into short = "
            + shortValue);
    }
}
```

**Output:**

```
1 after converting into short = 1

```

**方法 3:(使用 Short.valueOf()方法)**
[短类](https://www.geeksforgeeks.org/java-lang-short-class-java/)的 **valueOf()方法**将数据从其内部形式转换为人类可读的形式。

**语法:**

```
Short.valueOf(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```
// Java Program to convert string to short

class GFG {

    // Function to convert String to Short
    public static short convertStringToShort(String str)
    {

        // Convert string to short
        // using valueOf() method
        return Short.valueOf(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1";

        // The expected short value
        short shortValue;

        // Convert string to short
        shortValue = convertStringToShort(stringValue);

        // Print the expected short value
        System.out.println(
            stringValue
            + " after converting into short = "
            + shortValue);
    }
}
```

**Output:**

```
1 after converting into short = 1

```