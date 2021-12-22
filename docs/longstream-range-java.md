# Java 中的 LongStream 范围()

> 原文:[https://www.geeksforgeeks.org/longstream-range-java/](https://www.geeksforgeeks.org/longstream-range-java/)

**LongStream 范围(long startInclusive，long endExclusive)** 返回从 startInclusive(包含)到 endExclusive(排除)的顺序长流，增量为 1。

**语法:**

```java
static LongStream range(long startInclusive, long endExclusive)

```

**参数:**

*   **LongStream :** 原始长值元素的序列。*   **开始包含:**包含初始值。*   **endExclusive :** The exclusive upper bound.

    **返回值:**长元素范围的连续长流。

    **示例:**

    ```java
    // Implementation of LongStream range
    // (long startInclusive, long endExclusive)
    import java.util.*;
    import java.util.stream.LongStream;

    class GFG {

        // Driver code
        public static void main(String[] args)
        {
            // Creating an LongStream
            LongStream stream = LongStream.range(6L, 10L);

            // Displaying the elements in range
            // including the lower bound but
            // excluding the upper bound
            stream.forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    6
    7
    8
    9

    ```

    **注意:** LongStream 范围(long startInclusive，long endExclusive)基本上像 for 循环一样工作。递增值的等价序列可以按如下顺序产生:

    ```java
    for (int i = startInclusive; i < endExclusive ; i++) 
    {
     ...
     ...
     ...
    }

    ```