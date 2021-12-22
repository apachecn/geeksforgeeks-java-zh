# 如何用示例将 Java 中的字符串值转换为浮点值

> 原文:[https://www . geesforgeks . org/如何通过示例将字符串值转换为 java 中的浮点值/](https://www.geeksforgeeks.org/how-to-convert-a-string-value-to-float-value-in-java-with-examples/)

在 Java 中给定一个字符串“ **str** ，任务是将这个字符串转换成浮点类型。

**示例:**

```java
Input: str = "1.0"
Output: 1.0

Input: str = "3.14"
Output: 3.14

```

**方法 1:(天真方法)**
一种方法是遍历字符串，将数字一个接一个地添加到 float 类型中。这种方法不是一种有效的方法。

**方法二:(使用 Float.parseFloat()方法)**
最简单的方法就是使用 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)中 [Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)的 [parseFloat()方法](https://www.geeksforgeeks.org/float-parsefloat-method-in-java-with-examples/)。此方法接受要分析的字符串，并从中返回浮点类型。如果不可转换，此方法将引发错误。

**语法:**

```java
Float.parseFloat(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```java
// Java Program to convert string to float

class GFG {

    // Function to convert String to Float
    public static float convertStringToFloat(String str)
    {

        // Convert string to float
        // using parseFloat() method
        return Float.parseFloat(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1.0";

        // The expected float value
        float floatValue;

        // Convert string to float
        floatValue = convertStringToFloat(stringValue);

        // Print the expected float value
        System.out.println(
            stringValue
            + " after converting into float = "
            + floatValue);
    }
}
```

**Output:**

```java
1.0 after converting into float = 1.0

```

**示例 2:** 显示转换不成功

```java
// Java Program to convert string to float

class GFG {

    // Function to convert String to Float
    public static void convertStringToFloat(String str)
    {

        float floatValue;

        try {
            // Convert string to float
            // using parseFloat() method
            floatValue = Float.parseFloat(str);

            // Print the expected float value
            System.out.println(
                str
                + " after converting into float = "
                + floatValue);
        }
        catch (Exception e) {
            // Print the error
            System.out.println(
                str
                + " cannot be converted to float: "
                + e.getMessage());
        }
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String str1 = "";
        String str2 = null;
        String str3 = "GFG";

        // Convert string to float
        // using parseFloat() method
        convertStringToFloat(str1);
        convertStringToFloat(str2);
        convertStringToFloat(str3);
    }
}
```

**Output:**

```java
cannot be converted to float: empty String
null cannot be converted to float: null
GFG cannot be converted to float: For input string: "GFG"

```

**方法三:(使用 Float.valueOf()方法)**
[Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)的 **valueOf()方法**将数据从其内部形式转换为人类可读形式。

**语法:**

```java
Float.valueOf(str);

```

下面是上述方法的实现:

**示例 1:** 显示成功转换

```java
// Java Program to convert string to float

class GFG {

    // Function to convert String to Float
    public static float convertStringToFloat(String str)
    {

        // Convert string to float
        // using valueOf() method
        return Float.valueOf(str);
    }

    // Driver code
    public static void main(String[] args)
    {

        // The string value
        String stringValue = "1.0";

        // The expected float value
        float floatValue;

        // Convert string to float
        floatValue = convertStringToFloat(stringValue);

        // Print the expected float value
        System.out.println(
            stringValue
            + " after converting into float = "
            + floatValue);
    }
}
```

**Output:**

```java
1.0 after converting into float = 1.0

```