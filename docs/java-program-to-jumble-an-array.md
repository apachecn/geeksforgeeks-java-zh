# 混合数组的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-bum-a-array/](https://www.geeksforgeeks.org/java-program-to-jumble-an-array/)

给定一个大小为 N 的数组，任务是打乱数组的元素或任何其他排列。使用 Java 可以通过生成数组中元素的随机序列来填充数组。这种算法被称为费希尔-耶茨洗牌算法。

[费希尔-耶茨混洗算法](http://en.wikipedia.org/wiki/Fisher%E2%80%93Yates_shuffle#The_modern_algorithm)在 0(n)时间复杂度下工作。假设给定一个函数 rand()在 O(1)时间内生成一个随机数。从最后一个元素开始，用从整个数组中随机选择的元素替换它。现在考虑从 0 到 n-2(大小减少 1)的数组，重复直到我们遇到第一个元素。

**例:**

```
Input : arr[] = {1, 2, 3, 4}
Output: arr[] = {3, 2, 4, 1}

Input : arr[] = {5, 2, 3, 4}
Output: arr[] = {2, 4, 3, 5}

```

**算法:**

```
  for i from n - 1 downto 1 do
       j = random integer with 0 <= j <= i
       exchange a[j] and a[i]

```

下面是上述方法的实现:

T3】JavaT5

```
// Program to jumble an array  using Java
import java.util.Random;
import java.io.*;

public class GFG {
    public static void shuffleanarray(int[] a)
    {
        int n = a.length;
        Random random = new Random();
        // generating random number from list
        random.nextInt();

        for (int i = 0; i < n; i++) {

            // using random generated number
            int change = i + random.nextInt(n - i);

            // swapping elements to shuffle
            int holder = a[i];
            a[i] = a[change];
            a[change] = holder;
        }
    }
    public static void main(String[] args)
    {
        int[] a = new int[] { 0, 1, 2, 3, 4, 5, 6 };
        shuffleanarray(a);
        System.out.print("arr[] = {");
        for (int i : a) {
            System.out.print(i + " ");
        }
        System.out.print("}");
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 是数组的大小。