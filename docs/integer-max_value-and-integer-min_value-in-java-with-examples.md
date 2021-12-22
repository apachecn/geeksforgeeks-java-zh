# 整数。最大值和整数。Java 中的最小值示例

> 原文:[https://www . geesforgeks . org/integer-max _ value-and-integer-min _ value-in-Java-with-examples/](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/)

很多时候，在[竞技编程](https://www.geeksforgeeks.org/how-to-begin-with-competitive-programming/)中，需要给变量赋值，数据类型能容纳的最大或最小值，但是记住这么大又精确的数字出来是一件困难的工作。因此，Java 有常数来表示这些数字，这样就可以直接将这些数字赋给变量，而无需实际键入整数。

*   **<u>Integer.MAX_VALUE</u>**
    Integer.MAX_VALUE is a constant in the [Integer class](https://www.geeksforgeeks.org/java-lang-integer-class-java/) of [java.lang package](https://www.geeksforgeeks.org/java-lang-package-java/) that specifies that stores the maximum possible value for any integer variable in Java. The actual value of this is

    ```java
    2^31-1 = 2147483647

    ```

    **例 1:**

    ```java
    // Java program to show
    // the value of Integer.MAX_VALUE

    class GFG {

        // Driver code
        public static void main(String[] arg)
        {

            // Print the value of Integer.MAX_VALUE
            System.out.println("Integer.MAX_VALUE = "
                               + Integer.MAX_VALUE);
        }
    }
    ```

    **Output:**

    ```java
    Integer.MAX_VALUE = 2147483647

    ```