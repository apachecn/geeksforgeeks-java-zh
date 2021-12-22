# 最小化数组最大元素的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序最小化最大数组元素/](https://www.geeksforgeeks.org/java-program-to-minimize-the-maximum-element-of-an-array/)

给定两个整数 N 和 K。创建一个由 N 个正整数组成的数组，这样数组中所有元素的总和可以被 K 整除，并且数组中最大的元素是最小的可能元素。

你必须找到那个数组的最大元素。

**示例:**

> 输入:N=5，K=11
> 
> 产出:3
> 
> 说明:我们可以将数组创建为[2，2，2，2，3]。数组的和是 11，可被 K=11 整除，最大元素是 3，在这种情况下这是最小的可能。
> 
> 输入:N=4，K=3
> 
> 产出:2
> 
> 说明:我们可以将数组创建为[1，2，1，2]。数组的和是 6，可被 K=3 整除，最大元素是 2，在这种情况下这是最小的可能。

**进场:**

因为我们必须将所有 N 个数字都取正值，所以我们可以取的最小值是 1。所以，最初，数组的和是 N*1 = N

现在，有两种可能的情况

1.  如果 K 大于或等于 N:如果我们使数组的和等于 K，那么我们可以观察到最大元素也会被最小化。所以，现在我们要形成一个由 N 个正整数组成的数组，其和为 K，我们可以把 K/N 分布到所有的 N 个地方。如果数组的和仍然不等于 K，那么我们将增加一个元素 K-(N*(K/N))。因此，我们可以找到最小可能的最大元素。并且，我们将 K/N 值分配到每个地方，这样任何元素都不会变得那么大。
2.  如果 K 小于 N:因为初始和是 N，所以我们增加了我们的和，这样和可以被 K 整除，和是最小的可能。总和必须最小，因为我们也必须最小化最大元素。假设最优和是 S。所以，S 必须被 K 整除，S 将大于或等于 n。现在，这与第一种情况相同。

假设，在这两种情况下，最优和是 S。因此，给 N-1 个元素赋予 S/N 的底值，给其余元素赋予和/K 的顶值，将使和等于 S，并且它也能被 K 整除

现在，在总和/N 的最低值和总和/N 的最高值之间，最高值会更大。最后，最大元素将是总和/N 的上限值

**以下是上述方法的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Minimize the maximum element of an array

import java.io.*;
import java.lang.*;
import java.util.*;
public class Main {
    public static void main(String[] args)
    {
        // Given
        int N = 5;
        int K = 11;

        System.out.println("N is " +N);
        System.out.println("K is " +K);

        // variable sum stores the optimal Sum
        int sum = 0;

        // the first case
        if (K >= N) {

            // the optimal sum will be K
            // as we have to keep the sum as minimum as
            // possible and the sum has to divisible by K
            sum = K;
        }

        // the second case
        else {

            // we have to increment sum as
            // the sum is divisible by K
            // and sum is greater than or equal to N

            // the ceiling value of N/K will give the
            // minimum value that has to be multiplied by K
            // to get the optimal sum
            int times = (int)Math.ceil((double)N / (double)K);

            sum = times * K;
        }

        // maximum_element will the ceil value of sum/N
        int maximum_element
            = (int)Math.ceil((double)sum / (double)N);

        // print the maximum_element as answer
        System.out.println("Maximum element is " +maximum_element);
    }
}
```

**Output**

```java
N is 5
K is 11
Maximum element is 3
```

**时间复杂度:** O(1)

**辅助空间:** O(1)