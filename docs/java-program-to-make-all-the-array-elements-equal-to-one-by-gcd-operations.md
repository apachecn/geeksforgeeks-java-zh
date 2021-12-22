# 通过 GCD 运算使所有数组元素等于 1 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-make-all-the-array-elements-equal-by-gcd-operations/](https://www.geeksforgeeks.org/java-program-to-make-all-the-array-elements-equal-to-one-by-gcd-operations/)

给你一个由 N 个整数组成的数组。您的任务是使最终数组的所有元素等于 1。您可以执行以下操作任意次数(可能为零)。选择 Ai 和 Aj 的两个指数*、(0 <=i,j <n and="" replace="" ai="" aj="" both="" with="" the="" href="https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/">GCD(最大公约数)。</n>*

**示例:**

> **输入:** A[] = {2，4，6，9}
> 
> **输出:**是
> 
> **说明:**先选 4 和 9 他们的 GCD 会是 1，所以现在数组是{2，1，6，1}。现在，我们可以选择 2 和 1，它们的 GCD 是 1，所以数组变成{1，1，6，1}。最后我们可以用 6 选 1，因为他们的 GCD 是 1。因此，最终的数组变成{1，1，1，1}。所以，我们可以让所有的数组元素等于 1。
> 
> **输入:** A[] = {9，6，15}
> 
> **输出:**否

**天真方法:**

1.  如果我们得到任何一对的 GCD 等于 1，那么我们可以通过把那个数和 1 一个接一个地取来使所有的数组元素都为 1。
2.  所以，找到任何同素对存在与否，因为同素对的 GCD 等于 1。
3.  如果 GCD 对的值等于 1，则打印“是”。
4.  否则打印“否”。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to make all the array elements
// equal to one by GCD operations
import java.io.*;
import java.lang.*;
import java.util.*;
public class Main {

    // Function that returns whether it is possible or not
    // to make all the array elements equal to one (1)
    static boolean possible(int A[])
    {
        int n = A.length;
        // Check all the possible pairs
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                int gcd = gcd(A[i], A[j]);
                // If the gcd is equal to 1 , return true
                if (gcd == 1)
                    return true;
            }
        }
        return false;
    }
    // Recursive function to return gcd of a and b
    static int gcd(int a, int b)
    {
        if (b == 0)
            return a;
        return gcd(b, a % b);
    }
    // Driver Code
    public static void main(String[] args)
    {
        // Given Array
        int A[] = { 2, 4, 6, 9 };

        boolean answer = possible(A);

        System.out.println(answer == true ? "Yes" : "No");
    }
}
```

**Output**

```
Yes
```

**时间复杂度:** O(N^2*log N)，其中 n 是数组的长度。

**有效方法:**

1.  计算整个数组的 GCD。
2.  如果存在任何同素对，那么它们的 GCD 将是 1。
3.  所以在这之后，任何数字来了，GCD 都会保持 1。
4.  如果在任何时间点，GCD 变为 1，则打破循环并打印“是”。
5.  如果整个迭代后 GCD 的最终值不等于 1，则打印“否”。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to make all the array elements
// equal to one by GCD operations
import java.io.*;
import java.lang.*;
import java.util.*;
public class Main {

    // Function that returns whether it is possible or not
    // to make all the array elements equal to one (1)
    static boolean possible(int A[])
    {
        int n = A.length;

        int gcd = 0;
        // calculate GCD of the whole array
        for (int i = 0; i < n; i++) {
            gcd = gcd(gcd, A[i]);
            // If the gcd is equal to 1 , return true
            if (gcd == 1)
                return true;
        }
        return false;
    }
    // Recursive function to return gcd of a and b
    static int gcd(int a, int b)
    {
        if (b == 0)
            return a;
        return gcd(b, a % b);
    }
    // Driver Code
    public static void main(String[] args)
    {
        // Given Array
        int A[] = { 2, 4, 6, 9 };

        boolean answer = possible(A);

        System.out.println(answer == true ? "Yes" : "No");
    }
}
```

**Output**

```
Yes
```

**时间复杂度:** O(N*logM)，其中 N 是数组的长度，M 是数组的最小元素。