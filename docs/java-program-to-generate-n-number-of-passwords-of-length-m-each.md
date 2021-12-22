# Java 程序生成 N 个长度为 M 的密码

> 原文:[https://www . geesforgeks . org/Java-program-to-generate-n-number-of-password-length-m-each/](https://www.geeksforgeeks.org/java-program-to-generate-n-number-of-passwords-of-length-m-each/)

生成 N 个密码，每个密码长度为 m。返回的密码数量不超过长度 m

**示例:**

```
Input : N = 1, M = 3
Output: 571

Input : N = 2, M = 4
Output: 5671
        1987
```

**进场:**

*   导入用于创建随机数的随机包。
*   初始化变量 N 和 m。
*   创建一个长度为 N 的数组。
*   运行嵌套循环

1.  生成 N 个密码的第一个循环。
2.  用于创建长度为 M 的密码的第二个循环。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Generate N Number
// of Passwords of Length M Each
import java.util.Random;
import java.util.Scanner;

public class GFG {
    public static void main(String args[])
    {
        // create a object of random class
        Random r = new Random();
        // N is numbers of password
        int N = 5;
        // M is the length of passwords
        int M = 8;
        // create a array of store passwords
        int[] a = new int[N];

        // run for loop N time
        for (int j = 0; j < N; j++) {
            // run this loop M time for genarating
            // M length password
            for (int i = 0; i < M; i++) {
                // store the password in array
                System.out.print(a[j] = r.nextInt(10));
            }
            System.out.println();
        }
    }
}
```

**Output**

```
73807243
05081188
63921767
70426689
06272980
```

**时间复杂度:** O(N*M)，其中 N 为需要的密码个数，M 为每个密码的长度。