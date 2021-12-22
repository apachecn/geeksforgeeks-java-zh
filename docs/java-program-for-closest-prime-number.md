# 最接近素数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-for-close-prime-number/](https://www.geeksforgeeks.org/java-program-for-closest-prime-number/)

给定一个数字 N，你必须打印它最接近的质数。素数可以小于、等于或大于给定的数。

**条件:** 1 ≤ N ≤ 100000

**例:**

```
Input : 16
Output: 17

Explanation: The two nearer prime number of 16 are 13 and 17\. But among these, 
17 is the closest(As its distance is only 1(17-16) from the given number).

Input : 97
Output : 97

Explanation : The closest prime number in this case is the given number number 
itself as the distance is 0 (97-97).

```

**进场:**

1.  使用厄拉多塞[筛](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)将所有质数存储在[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)中。
2.  将矢量中的所有元素复制到新数组中。
3.  使用上限查找数组中给定数字的上限。
4.  由于数组本质上已经排序过了，比较数组中以前和当前的索引号。
5.  返回差异最小的数字。

下面是该方法的实现。

## 爪哇

```
// Closest Prime Number in Java

import java.util.*;
import java.lang.*;

public class GFG {

    static int max = 100005;

    static Vector<Integer> primeNumber = new Vector<>();

    static void sieveOfEratosthenes()
    {

        // Create a boolean array "prime[0..n]" and
        // initialize all entries it as true. A value
        // in prime[i] will finally be false if i is
        // Not a prime, else true.
        boolean prime[] = new boolean[max + 1];
        for (int i = 0; i <= max; i++)
            prime[i] = true;

        for (int p = 2; p * p <= max; p++) {

            // If prime[p] is not changed, then it is a
            // prime
            if (prime[p] == true) {

                // Update all multiples of p
                for (int i = p * p; i <= max; i += p)
                    prime[i] = false;
            }
        }

        // Print all prime numbers
        for (int i = 2; i <= max; i++) {

            if (prime[i] == true)
                primeNumber.add(i);
        }
    }

    static int upper_bound(Integer arr[], int low, int high,
                           int X)
    {
        // Base Case
        if (low > high)
            return low;

        // Find the middle index
        int mid = low + (high - low) / 2;

        // If arr[mid] is less than
        // or equal to X search in
        // right subarray
        if (arr[mid] <= X) {
            return upper_bound(arr, mid + 1, high, X);
        }

        // If arr[mid] is greater than X
        // then search in left subarray
        return upper_bound(arr, low, mid - 1, X);
    }

    public static int closetPrime(int number)
    {

        // We will handle it (for number = 1) explicitly
        // as the lower/left number of 1 can give us
        // negative index which will cost Runtime Error.
        if (number == 1)
            return 2;
        else {

            // calling seive of eratosthenes to
            // fill the array into prime numbers
            sieveOfEratosthenes();

            Integer[] arr = primeNumber.toArray(
                new Integer[primeNumber.size()]);
            // searching the index
            int index
                = upper_bound(arr, 0, arr.length, number);

            if (arr[index] == number
                || arr[index - 1] == number)
                return number;
            else if (Math.abs(arr[index] - number)
                     < Math.abs(arr[index - 1] - number))
                return arr[index];
            else
                return arr[index - 1];
        }
    }
    // Driver Program
    public static void main(String[] args)
    {
        int number = 100;
        System.out.println(closetPrime(number));
    }
}
```

**输出**

```
101

```

**时间复杂度:** O(N log(log(N)))

**空间复杂度:** O(N)