# 如何在 Java 中生成特定范围内的随机整数？

> 原文:[https://www . geeksforgeeks . org/如何生成 java 中特定范围内的随机整数/](https://www.geeksforgeeks.org/how-do-i-generate-random-integers-within-a-specific-range-in-java/)

给定两个数字 **Min** 和 **Max** ，任务是在 Java 中生成这个特定范围内的随机整数。

**例:**

```
Input: Min = 1, Max = 100
Output: 89

Input: Min = 100, Max = 899
Output: 514

```

**逼近:**

*   Gets the minimum and maximum values in the specified range.
*   沙吾提线程局部随机 1860 年(Java)。使用中。竞争对手。线程局部随机)什么事 **nextInt()凯伊姆，是吗 Min(最小)你好-麦克斯魏冄

    ```
    ThreadLocalRandom.current().nextInt(min, max + 1);
    ```** 
*   The random value received.

```
// Java program to generate a random integer
// within this specific range

import java.util.concurrent.ThreadLocalRandom;

class GFG {

    public static int getRandomValue(int Min, int Max)
    {

        // Get and return the random integer
        // within Min and Max
        return ThreadLocalRandom
            .current()
            .nextInt(Min, Max + 1);
    }

    // Driver code
    public static void main(String[] args)
    {

        int Min = 1, Max = 100;

        System.out.println("Random value between "
                           + Min + " and " + Max + ": "
                           + getRandomValue(Min, Max));
    }
}
```

**输出:**

```
Random value between 1 and 100: 35

```