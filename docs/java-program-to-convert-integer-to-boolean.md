# 将整数转换为布尔值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-整数-布尔/](https://www.geeksforgeeks.org/java-program-to-convert-integer-to-boolean/)

给定一个整数值，任务是将这个[整数值](https://www.geeksforgeeks.org/java-lang-integer-class-java/)转换成 Java 中的[布尔值](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)。

**示例:**

```java
Input: int = 1
Output: true

Input: int = 0
Output: false

```

**进场:**

*   获取要转换的布尔值。
*   检查布尔值是真还是假
*   如果整数值大于或等于 1，则将布尔值设置为 true。
*   否则，如果整数值大于 1，则将布尔值设置为 false。

**例 1:**

```java
// Java Program to convert integer to boolean

public class GFG {

    public static void main(String[] args)
    {

        // The integer value
        int intValue = 1;

        // The expected boolean value
        boolean boolValue;

        // Check if it's greater than equal to 1
        if (intValue >= 1) {
            boolValue = true;
        }
        else {
            boolValue = false;
        }

        // Print the expected integer value
        System.out.println(
            intValue
            + " after converting into boolean = "
            + boolValue);
    }
}
```

**Output:**

```java
1 after converting into boolean = true

```

**例 2:**

```java
// Java Program to convert integer to boolean

public class GFG {

    public static void main(String[] args)
    {

        // The integer value
        int intValue = 0;

        // The expected boolean value
        boolean boolValue;

        // Check if it's greater than equal to 1
        if (intValue >= 1) {
            boolValue = true;
        }
        else {
            boolValue = false;
        }

        // Print the expected integer value
        System.out.println(
            intValue
            + " after converting into boolean = "
            + boolValue);
    }
}
```

**Output:**

```java
0 after converting into boolean = false

```