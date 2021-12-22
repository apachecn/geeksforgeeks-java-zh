# 竞争编程的 Java 技巧(针对 Java 8)

> 原文:[https://www . geesforgeks . org/Java-ticks-competitive-programming-Java-8/](https://www.geeksforgeeks.org/java-tricks-competitive-programming-java-8/)

虽然练习是确保在编程竞赛中提高性能的唯一方法，但是掌握一些技巧可以确保优势和快速调试。
**1)在不使用%运算符的情况下检查数字是偶数还是奇数:**
虽然这个技巧并不比使用%运算符好多少，但有时很有效(对于大数)。

**使用&运算符:**

```
System.out.println((a & 1) == 0 ?  "EVEN" : "ODD" );
```

**示例:**

```
num = 5 
Binary: "101 & 1" will be 001, so false 

num = 4 
Binary: "100 & 1" will be 000, so true.
```

**2)快速乘除 2**

乘以 2 意味着向左移动所有位，除以 2 意味着向右移动。

**示例:** 2(二进制 10):向左移动 4(二进制 100)和向右移动 1(二进制 1)

```
n = n << 1;   // Multiply n with 2
n = n >> 1;   // Divide n by 2
```

**3)使用异或进行 2 个数字的交换:**

这个方法很快，不需要使用第三个变量。

```
  // A quick way to swap a and b
  a ^= b;
  b ^= a;
  a ^= b; 
```

**4)更快的输入输出:**

关于 java 中的快速输入/输出，请参考这里的

**5)对于字符串操作:**

使用 [StringBuffer](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) 进行字符串操作，因为 java 中的[字符串](https://www.geeksforgeeks.org/g-fact-27-string-vs-stringbuilder-vs-stringbuffer/)是不可变的。在此参考。

**6)计算最高有效位:**

要计算任意数字的最高有效位，可以直接用对数来计算。

```
Suppose the number is N then 
Let double K = Math.log10(N);
now K = K - Math.floor(K);
int X = (int)Math.pow(10, K);
X will be the most significant digit. 
```

**7)直接计算位数:**

为了计算数字中的位数，我们可以有效地使用 log，而不是循环:

```
No. of digits in N = Math.floor(Math.log10(N)) + 1;
```

**8)内置 GCD 方法:**

Java 在 [BigInteger 类](https://www.geeksforgeeks.org/biginteger-class-in-java/)中内置了 GCD 方法。它返回一个 BigInteger，其值是 abs(this)和 abs(val)的最大公约数。如果该值==0 &则返回 0。

**语法:**

```
public BigInteger gcd(BigInteger val)
Parameters :
val - value with which the GCD is to be computed.
Returns :
GCD(abs(this), abs(val))
```

以下是全球合作对话的实施情况:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how
// to use gcd method of BigInteger class

import java.math.BigInteger;

class Test {
    public static int gcd(int a, int b)
    {
        BigInteger b1 = BigInteger.valueOf(a);
        BigInteger b2 = BigInteger.valueOf(b);
        BigInteger gcd = b1.gcd(b2);
        return gcd.intValue();
    }

    public static long gcd(long a, long b)
    {
        BigInteger b1 = BigInteger.valueOf(a);
        BigInteger b2 = BigInteger.valueOf(b);
        BigInteger gcd = b1.gcd(b2);
        return gcd.longValue();
    }

    // Driver method
    public static void main(String[] args)
    {
        System.out.println(gcd(3, 5));
        System.out.println(gcd(10000000000L, 600000000L));
    }
}
```

**Output**

```
1
200000000

```

**9)检查素数:**

Java 在 [BigInteger 类](https://www.geeksforgeeks.org/biginteger-class-in-java/)中有一个内置的 isProbablePrime()方法。如果这个大整数可能是质数(有一定把握)，它返回真；如果它肯定是复合的，它返回假。

```
BigInteger.valueOf(1235).isProbablePrime(1) 
```

**10)** [**知道一个数是否是 2 的幂的高效技巧**](https://www.geeksforgeeks.org/program-to-find-whether-a-no-is-power-of-two/) **:**

除法的常规技巧复杂度是 O(logN)，但它可以用 O(v)来求解，其中 v 是二进制形式的数字位数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
/* Method to check if x is power of 2*/
static boolean isPowerOfTwo (int x)
{
     /* First x in the below expression is
     for the case when x is 0 */
      return x!=0 && ((x&(x-1)) == 0);   
}
```

**11)排序算法:**

1.  [Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 用于对数组的元素进行排序。
2.  [Collections.sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) 用于对集合的元素进行排序。

对于基元，Arrays.sort()使用[双轴快速排序](https://www.geeksforgeeks.org/3-way-quicksort-dutch-national-flag/)算法。

**12)搜索算法:**

1.  arrays . binary search()([SET 1](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/)|[SET 2](https://www.geeksforgeeks.org/arrays-binarysearch-in-java-with-examples-set-2-search-in-subarray/))用于在排序的数组上应用二分搜索法。
2.  [collections . binary search()](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)用于对基于比较器的集合应用二分搜索法。

**13)复制算法:**

1.  [Arrays.copyOf()和 copy for range()](http://contribute.geeksforgeeks.org/wp-admin/post.php?post=188444&action=edit)复制指定的数组。
2.  [Collections.copy()](https://docs.oracle.com/javase/7/docs/api/java/util/Collections.html#copy(java.util.List, %20java.util.List)) 复制指定的集合。

**14)旋转和频率**

我们可以使用 [Collections.rotate()](https://www.geeksforgeeks.org/java-util-collections-rotate-method-java-examples/) 将集合或数组旋转指定的距离。也可以使用 [Collections.frequency()](https://www.geeksforgeeks.org/java-util-collections-frequency-java-examples/) 方法获取集合或数组中指定元素的频率。

**15)大部分数据结构已经在** [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 中实现。

例如[栈](https://www.geeksforgeeks.org/stack-class-in-java/)、[链表](https://www.geeksforgeeks.org/linked-list-in-java/)、 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 、[hashmap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)、[堆](https://www.geeksforgeeks.org/priority-queue-class-in-java-2/)等。

**16)使用** [**包装类**](https://www.geeksforgeeks.org/wrapper-classes-java/) **函数获取一个数的基数转换**有时候你需要一个数的基数转换。为此，您可以使用包装类。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate use of wrapper
// classes for radix conversion

class Test {
    // Driver method
    public static void main(String[] args)
    {
        int a = 525;
        long b = 12456545645L;

        String binaryA = Integer.toString(a, 2);
        System.out.println("Binary representation"
                           + " of A : " + binaryA);
        String binaryB = Long.toString(b, 2);
        System.out.println("Binary representation"
                           + " of B : " + binaryB);
        String octalA = Integer.toString(a, 8);
        System.out.println("Octal representation"
                           + " of A : " + octalA);
        String octalB = Long.toString(b, 8);
        System.out.println("Octal representation"
                           + " of B : " + octalB);
    }
}
```

**Output**

```
Binary representation of A : 1000001101
Binary representation of B : 1011100110011101111100110101101101
Octal representation of A : 1015
Octal representation of B : 134635746555

```

**17) NullPointerException(为什么？)**这里参考这里参考避开。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。