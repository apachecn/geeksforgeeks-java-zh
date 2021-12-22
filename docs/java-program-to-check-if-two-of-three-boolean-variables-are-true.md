# 检查三个布尔变量中两个是否为真的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查三个布尔变量中的两个是否为真/](https://www.geeksforgeeks.org/java-program-to-check-if-two-of-three-boolean-variables-are-true/)

**布尔**值为**真/假**。在这个程序中，我们需要检查三个布尔值中是否有两个是真的。

我们将讨论两种主要的方法来做到这一点:

1.  使用 [**if-else**](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/) 。
2.  使用 [**三元**](https://www.geeksforgeeks.org/ternary-search-tree/) 运算符。

**方法 1:使用** **if-else 条件**

我们初始化三个布尔变量标志，一个布尔值为假，一个值为真。

通过增加每个真值的计数器值，可以使用**计数器方法**检查这三个布尔变量中是否有两个为真。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check if
// two out of three boolean
// variables are true

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        boolean flag1 = true;
        boolean flag2 = true;
        boolean flag3 = false;

        // maintaining a counter
        int cnt = 0;

        // check if flag1 is true, increment counter
        if (flag1)
            cnt += 1;

        // check if flag2 is true, increment counter
        if (flag2)
            cnt += 1;

        // check if flag3 is true, increment counter
        if (flag3)
            cnt += 1;

        // check counter value
        if (cnt == 2)

            System.out.println("Two flags are true!");

        else

            System.out.println("Two flags are not true!");
    }
}
```

**Output**

```
Two flags are true!
```

*   **时间复杂度:** O(1)
*   **空间复杂度:** O(1)

**另一种方法:**这里，我们检查 flag1 是否为真，如果 flag2 或 flag3 中有一个为真，那么 ans 应该为真。否则，如果 flag1 为假，那么当 flag2 和 flag3 都为真时，ans 将为真。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check 
// if two out of three boolean
// variables are true

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        boolean flag1 = true;
        boolean flag2 = true;
        boolean flag3 = false;

        // to store the result
        boolean ans = false;

        if (flag1) {
           ans = flag2 || flag3;
        }
        else {
            ans = flag2 && flag3;
        }

        if (ans)
            System.out.println("Two flags are true!");
        else
            System.out.println("Two flags are not true!");
    }
}
```

**Output**

```
Two flags are true!
```

*   **时间复杂度:** O(1)
*   **空间复杂度:** O(1)

**方法 3:使用** **三元运算符**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to check if
// two out of three boolean
// variables are true
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        boolean flag1 = true;
        boolean flag2 = true;
        boolean flag3 = true;

        // to store the result
        boolean ans = false;

        ans = flag1 ? flag2 || flag3 : flag2 && flag3;

        if (ans)
            System.out.println("Two flags are true!");
        else
            System.out.println("Two flags are not true!");
    }
}
```

**Output**

```
Two flags are not true!
```

*   **时间复杂度:** O(1)
*   **空间复杂度:** O(1)