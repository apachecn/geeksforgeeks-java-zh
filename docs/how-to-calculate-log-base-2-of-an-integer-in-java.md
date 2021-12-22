# 在 Java 中如何计算一个整数的对数基数 2？

> 原文:[https://www . geesforgeks . org/如何计算 java 中整数的对数基数 2/](https://www.geeksforgeeks.org/how-to-calculate-log-base-2-of-an-integer-in-java/)

给定一个整数 **N** ，任务是计算其到 base 2 的 log，即 Java 中 log <sub>2</sub> N。

**示例:**

```java
Input: N = 2
Output: 1

Input: 1024
Output: 10

```

**进场:**

*   [Java 中的 Math 类(java.lang.Math)](https://www.geeksforgeeks.org/java-lang-math-class-in-java-set-1/) 是一个保存计算此类值的函数的库，如 [sin()](https://www.geeksforgeeks.org/java-math-sin-method-examples/) 、 [cos()](https://www.geeksforgeeks.org/java-math-cos-method-examples/) 、 [log()](https://www.geeksforgeeks.org/java-math-log-method-example/) 等。但是数学课中的 [log()方法计算的是基数为 10 的对数。因此，在 Java 中没有直接的方法来计算到 base 2 的日志。](https://www.geeksforgeeks.org/java-math-log-method-example/)
*   但是我们知道

    ```java
    loga b = log10 b / log10 a
    ```

*   Therefore we can calculate log<sub>2</sub> N indirectly as:
    **log<sub>2</sub> N = log<sub>10</sub> N / log<sub>10</sub> 2**

    下面是上述方法的实现:

    ```java
    // Java code to Calculate log base 2 of an integer

    import java.io.*;
    import java.lang.*;

    class GFG {

        // Function to calculate the
        // log base 2 of an integer
        public static int log2(int N)
        {

            // calculate log2 N indirectly
            // using log() method
            int result = (int)(Math.log(N) / Math.log(2));

            return result;
        }

        // Driver code
        public static void main(String[] args)
        {

            int N = 1024;

            System.out.println("Log " + N
                               + " to the base 2 = "
                               + log2(N));
        }
    }
    ```

    **Output:**

    ```java
    Log 1024 to the base 2 = 10

    ```