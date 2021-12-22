# 将布尔转换为整数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-布尔到整数/](https://www.geeksforgeeks.org/java-program-to-convert-boolean-to-integer/)

给定一个布尔值，任务是将这个[布尔值](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)转换为 Java 中的[整数值](https://www.geeksforgeeks.org/java-lang-integer-class-java/)。

**示例:**

```
Input: boolean = true
Output: 1

Input: boolean = false
Output: 0

```

**进场:**

*   获取要转换的布尔值。
*   检查布尔值是真还是假
*   如果布尔值为真，则将整数值设置为 1。
*   否则，如果布尔值为 false，则将整数值设置为 0。

下面是上述方法的实现:

**示例 1:** 当布尔值为真时

```
// Java Program to convert boolean to integer

public class GFG {

    public static void main(String[] args)
    {

        // The boolean value
        boolean boolValue = true;

        // The expected integer value
        int intValue;

        // Check if it's true or false
        if (boolValue) {
            intValue = 1;
        }
        else {
            intValue = 0;
        }

        // Print the expected integer value
        System.out.println(
            boolValue
            + " after converting into integer = "
            + intValue);
    }
}
```

**Output:**

```
true after converting into integer = 1

```

**示例 2:** 当布尔值为假时

```
// Java Program to convert boolean to integer

public class GFG {

    public static void main(String[] args)
    {

        // The boolean value
        boolean boolValue = false;

        // The expected integer value
        int intValue;

        // Check if it's true or false
        if (boolValue) {
            intValue = 1;
        }
        else {
            intValue = 0;
        }

        // Print the expected integer value
        System.out.println(
            boolValue
            + " after converting into integer = "
            + intValue);
    }
}
```

**Output:**

```
false after converting into integer = 0

```