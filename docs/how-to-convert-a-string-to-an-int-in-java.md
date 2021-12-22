# 如何在 Java 中将字符串转换为 Int？

> 原文:[https://www . geesforgeks . org/如何在 java 中将字符串转换为 int/](https://www.geeksforgeeks.org/how-to-convert-a-string-to-an-int-in-java/)

给定包含数字作为字符的字符串，任务是在 Java 中将这个给定的字符串转换成整数。

**示例:**

```
Input: str = "1234"
Output: 1234

Input: str = "213s"
Output: 0
Since the String contains other than digits,
hence the integer value will be 0

```

*   **Method 1: Use [Integer.parseInt()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/) method**
    This is the most simple method to convert String to integer. This function parses the string argument as a signed decimal integer.

    **语法:**

    ```
    public static int parseInt(String s)
                throws NumberFormatException

    ```

    下面是上述方法的实现:

    ```
    // Java program to convert String to int
    // using Integer.parseInt() method

    import java.io.*;

    class GFG {

        // Function to convert String to integer
        public static int convert(String str)
        {
            int val = 0;
            System.out.println("String = " + str);

            // Convert the String
            try {
                val = Integer.parseInt(str);
            }
            catch (NumberFormatException e) {

                // This is thrown when the String
                // contains characters other than digits
                System.out.println("Invalid String");
            }
            return val;
        }

        // Driver code
        public static void main(String[] args)
        {

            String str = "1234";
            int val = convert(str);
            System.out.println("Integer value = " + val);
            System.out.println();

            str = "123s";
            val = convert(str);
            System.out.println("Integer value = " + val);
        }
    }
    ```

    **Output:**

    ```
    String = 1234
    Integer value = 1234

    String = 123s
    Invalid String
    Integer value = 0

    ```

*   **Method 2: Use Ints::tryParse method of Guava library**
    Another method to convert String to integer is to use Ints::tryParse method of Guava library. It is similar to the Integer.parseInt() method, but this method is more concise and powerful.

    **语法:**

    ```
    public static Integer tryParse(String s)

    ```

    下面是上述方法的实现:

    ```
    // Java program to convert String to int
    // using Ints::tryParse method

    import java.io.*;
    import java.util.*;
    import com.google.common.primitives.Ints;

    class GFG {

        // Function to convert String to integer
        public static int convert(String str)
        {
            int val = 0;
            System.out.println("String = " + str);

            // Convert the String
            val = Optional.ofNullable(str)
                      .map(Ints::tryParse)
                      .orElse(0);

            return val;
        }

        // Driver code
        public static void main(String[] args)
        {

            String str = "1234";
            int val = convert(str);
            System.out.println("Integer value = " + val);
            System.out.println();

            str = "123s";
            val = convert(str);
            System.out.println("Integer value = " + val);
        }
    }
    ```

    **Output:**

    ```
    String = 1234
    Integer value = 1234

    String = 123s
    Integer value = 0

    ```