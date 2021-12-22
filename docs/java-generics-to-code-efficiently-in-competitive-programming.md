# 在竞争性编程中高效编码的 Java 泛型

> 原文:[https://www . geesforgeks . org/Java-泛型到代码的高效竞争编程/](https://www.geeksforgeeks.org/java-generics-to-code-efficiently-in-competitive-programming/)

[模板](https://www.geeksforgeeks.org/templates-in-c-vs-generics-in-java/)是泛型编程的基础，它涉及以独立于任何特定类型的方式编写代码。这些强大的工具可以用来有效地编写我们的代码。在[竞技编程](https://www.geeksforgeeks.org/how-to-begin-with-competitive-programming/)中可能用到的一些很酷的技巧如下:

### [**<u>快速输入/输出</u>**](https://www.geeksforgeeks.org/fast-io-in-java-in-competitive-programming/) **:**

这利用了[buffere reader](https://www.geeksforgeeks.org/java-io-bufferedreader-class-java/)和 [StringTokenizer](https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/) 的时间优势和用户定义方法的优势，减少了输入，因此输入速度更快。下面是使用快速读写器求 **N** 整数之和的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the fast
// input output
import java.io.*;
import java.util.StringTokenizer;

public class GFG {

    // Driver Code
    public static void main(String[] args)
        throws IOException
    {

        // Initialize the reader
        FastReader reader = new FastReader();

        // Initialize the writer
        FastWriter writer = new FastWriter();

        // Your Code here

        // Reads a single integer
        int n = reader.readSingleInt();

        // Reads a array of N number
        // in a line
        int a[] = reader.readIntArray(n);

        // Prints a string
        writer.writeString("SUM OF :");

        // Print the array of number
        // with spaces
        writer.writeIntArrayWithSpaces(a);

        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += a[i];
        }

        // Prints a single number
        writer.writeSingleInteger(sum);
    }

    // Fast Reader Class
    public static class FastReader {

        // Reader object
        BufferedReader reader;

        // Constructor
        public FastReader()
        {
            // Initialize the reader
            reader = new BufferedReader(
                new InputStreamReader(
                    System.in));
        }

        // String tokenizer
        StringTokenizer tokenizer;

        // Function to read integer
        public int readSingleInt()
            throws IOException
        {
            return Integer.parseInt(
                reader.readLine());
        }

        // Function to read a single long
        public long readSingleLong()
            throws IOException
        {
            return Long.parseLong(
                reader.readLine());
        }

        // Function to read a array of
        // numsInts integers in 1 line
        public int[] readIntArray(int numInts)
            throws IOException
        {
            int[] nums = new int[numInts];
            tokenizer
                = new StringTokenizer(
                    reader.readLine());

            // Input Numbers
            for (int i = 0; i < numInts; i++) {
                nums[i] = Integer.parseInt(
                    tokenizer.nextToken());
            }
            return nums;
        }

        // Function to read string
        public String readString()
            throws IOException
        {
            return reader.readLine();
        }
    }

    // Fast Writer Class
    public static class FastWriter {

        // Writer object
        BufferedWriter writer;

        // Constructor
        public FastWriter()
        {

            // Initialize the writer
            writer = new BufferedWriter(
                new OutputStreamWriter(
                    System.out));
        }

        // Function to write single integer
        public void writeSingleInteger(int i)
            throws IOException
        {
            writer.write(Integer.toString(i));
            writer.newLine();
            writer.flush();
        }

        // Function to write a single long
        public void writeSingleLong(long i)
            throws IOException
        {
            writer.write(Long.toString(i));
            writer.newLine();
            writer.flush();
        }

        // Function to write a Integer
        // of array with spaces in 1 line
        public void writeIntArrayWithSpaces(
            int[] nums)
            throws IOException
        {
            for (int i = 0; i < nums.length; i++) {
                writer.write(nums[i] + " ");
            }
            writer.newLine();
            writer.flush();
        }

        // Function to write a Integer
        // of array without spaces
        // in 1 line
        public void writeIntArrayWithoutSpaces(int[] nums)
            throws IOException
        {
            for (int i = 0;
                 i < nums.length; i++) {
                writer.write(
                    Integer.toString(
                        nums[i]));
            }
            writer.newLine();
            writer.flush();
        }

        // Function to write a String
        public void writeString(String s)
            throws IOException
        {
            writer.write(s);
            writer.newLine();
            writer.flush();
        }
    }
}
```

为了将基于环境的输入和输出流更改为文本文件或标准输入，就像使用高级文本或其他 ide 时通常做的那样，使用下面的代码作为 FastIO 的模板。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// fast input output
import java.io.*;
import java.util.StringTokenizer;

public class GFG {
    public

        // Driver Code
        static void main(String[] args) throws IOException
    {

        // Initialize the reader
        FastReader reader = new FastReader();

        // Initialize the writer
        FastWriter writer = new FastWriter();

        // Your Code here
    }

    // Fast Reader Class
    public static class FastReader {

        // Reader object
        BufferedReader reader;

        // Constructor
        public FastReader()
        {

            // Initialize the reader
            reader = new BufferedReader(
                new InputStreamReader(
                    System.in));

            if (System.getProperty(
                    "ONLINE_JUDGE")
                == null) {
                try {
                    reader = new BufferedReader(
                        new InputStreamReader(
                            new FileInputStream(
                                "input.txt")));
                }
                catch (Exception e) {
                }
            }
        }

        // String tokenizer
        StringTokenizer tokenizer;

        // Function to read a
        // single integer
        public int readSingleInt()
            throws IOException
        {
            return Integer.parseInt(
                reader.readLine());
        }

        // Function to read a
        // single long
        public long readSingleLong()
            throws IOException
        {
            return Long.parseLong(
                reader.readLine());
        }

        // Function to read a array
        // of numsInts integers
        // in one line
        public int[] readIntArray(int numInts)
            throws IOException
        {
            int[] nums = new int[numInts];
            tokenizer
                = new StringTokenizer(
                    reader.readLine());

            for (int i = 0;
                 i < numInts; i++) {
                nums[i] = Integer.parseInt(
                    tokenizer.nextToken());
            }
            return nums;
        }

        // Function to read string
        public String readString()
            throws IOException
        {
            return reader.readLine();
        }
    }

    // Fast Writer Class
    public static class FastWriter {

        // Writer object
        BufferedWriter writer;

        // Constructor
        public FastWriter()
        {

            // Initialize the writer
            writer = new BufferedWriter(
                new OutputStreamWriter(
                    System.out));
            if (System.getProperty(
                    "ONLINE_JUDGE")
                == null) {
                try {
                    writer = new BufferedWriter(
                        new OutputStreamWriter(
                            new FileOutputStream(
                                "output.txt")));
                }
                catch (Exception e) {
                }
            }
        }

        // Function to write the
        // single integer
        public void writeSingleInteger(int i)
            throws IOException
        {
            writer.write(Integer.toString(i));
            writer.newLine();
            writer.flush();
        }

        // Function to write single long
        public void writeSingleLong(long i)
            throws IOException
        {
            writer.write(Long.toString(i));
            writer.newLine();
            writer.flush();
        }

        // Function to write a Integer of
        // array with spaces in one line
        public void writeIntArrayWithSpaces(int[] nums)
            throws IOException
        {
            for (int i = 0;
                 i < nums.length; i++) {
                writer.write(nums[i]
                             + " ");
            }
            writer.newLine();
            writer.flush();
        }

        // Function to write Integer of
        // array without spaces in 1 line
        public void writeIntArrayWithoutSpaces(int[] nums)
            throws IOException
        {
            for (int i = 0;
                 i < nums.length; i++) {
                writer.write(
                    Integer.toString(
                        nums[i]));
            }
            writer.newLine();
            writer.flush();
        }

        // Function to write String
        public void writeString(String s)
            throws IOException
        {
            writer.write(s);
            writer.newLine();
            writer.flush();
        }
    }
}
```

**<u>注</u> :** 以上 Java 快速输入输出信息请参考[本帖](https://www.geeksforgeeks.org/fast-io-in-java-in-competitive-programming/)。

### **<u>竞技编程中常用的功能</u> :**

以下是[竞技编程](https://www.geeksforgeeks.org/category/competitive-programming/)中常用的功能，可以将其包含在代码中，避免在比赛中浪费时间实现。

### [**<u>成对出现在爪哇</u>**](https://www.geeksforgeeks.org/pair-class-in-java/) **:**

成对常用于竞技编程。在 JAVA 中使用对是一种简单的方法。下面是同样的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// use Pairs
import java.io.*;

class GFG {

    // Driver Code
    public static void main(String[] args)
    {
        // Initialize a pair
        Pair<Integer, Integer> x
            = new Pair<Integer, Integer>(1, 2);

        // Print pair
        System.out.println(x.first + ", "
                           + x.second);
    }

    // Pair class
    static class Pair<A, B> {
        A first;
        B second;

        // Constructor
        public Pair(A first, B second)
        {
            this.first = first;
            this.second = second;
        }
    }
}
```

### [**<u>快速指数使用 mod</u>**](https://www.geeksforgeeks.org/modular-exponentiation-power-in-modular-arithmetic/) **:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Function to find x ^ n using p as mod
static long power(long x, long y, long p)
{

    // Initialize result
    long res = 1;

    // Update x if it is more than or
    // equal to p
    x = x % p;

    while (y > 0) {

        // If y is odd, multiply x
        // with result
        if (y % 2 == 1)
            res = (res * x) % p;

        // y must be even now
        y = y >> 1; // y = y/2
        x = (x * x) % p;
    }

    return res;
}
```

### **<u>nCr 使用</u>** [**<u>费马小定理</u>**](https://www.geeksforgeeks.org/fermats-little-theorem/) **:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Function to find x ^ n using p as mod
static long power(long x, long y, long p)
{

    // Initialize result
    long res = 1;

    // Update x if it is more than or
    // equal to p
    x = x % p;

    while (y > 0) {

        // If y is odd, multiply x
        // with result
        if (y % 2 == 1)
            res = (res * x) % p;

        // y must be even now
        y = y >> 1; // y = y/2
        x = (x * x) % p;
    }

    return res;
}

// Returns n^(-1) mod p
static long modInverse(long n, long p)
{
    return power(n, p - 2, p);
}

// Returns nCr % p using Fermat's
// little theorem.
static long nCrModPFermat(int n, int r, long p)
{

    // Base case
    if (r == 0)
        return 1;

    // Fill factorial array so that we
    // can find all factorial of r, n
    // and n-r
    long[] fac = new long[n + 1];
    fac[0] = 1;

    for (int i = 1; i <= n; i++)
        fac[i] = fac[i - 1] * i % p;

    return (fac[n] * modInverse(fac[r], p) % p
            * modInverse(fac[n - r], p) % p)
        % p;
}
```

### [**<u>二项式系数</u>**](https://www.geeksforgeeks.org/space-and-time-efficient-binomial-coefficient/) **:**

二项式系数多用于求[N *(N–1)*—*(N–K+1)]/[K *(K–1)*—-* 1]的值。下面是实现相同的程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Function to implement the
// binomial coefficient
static long binomialCoeff(long n,
                          long k,
                          long MOD)
{
    long res = 1;

    // Since C(n, k) = C(n, n-k)
    if (k > n - k)
        k = n - k;

    // Find the value of
    // [n * (n-1) *---* (n-k+1)] / [k * (k-1) *----* 1]
    for (int i = 0; i < k; ++i) {
        res *= (n - i);
        res /= (i + 1);
        res %= MOD;
    }

    // Return the result
    return res;
}
```

### [**<u>模运算</u>**](https://www.geeksforgeeks.org/modular-arithmetic/) **:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
const int mod = 1000000007;

// Function to implement the modular
// arithmetic addition
private static long modular_add(long a, long b)
{
    return ((a % mod) + (b % mod)) % mod;
}

// Function to implement the modular
// arithmetic subtraction
private static long modular_sub(long a, long b)
{
    return ((a % mod) - (b % mod) + mod) % mod;
}

// Function to implement the modular
// arithmetic multiplication
private static long modular_mult(long a, long b)
{
    return ((a % mod) * (b % mod)) % mod;
}
```

### [**<u>排序数组</u>**](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) **:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Function to sort an integer array
static void sort(int[] a)
{
    // Stores the element in arraylist
    ArrayList<Integer> l = new ArrayList<>();
    for (int i : a)
        l.add(i);

    // Use collection.sort() method
    Collections.sort(l);

    // Update the original array
    // with the sorted array elements
    for (int i = 0; i < a.length; i++)
        a[i] = l.get(i);
}
```

### [**<u>GCD 和 LCM</u>**T5**:**](https://www.geeksforgeeks.org/mathematical-algorithms/mathematical-algorithms-gcd-lcm/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
static long lcm(int a, int b)
{
    return (a / gcd(a, b)) * b;
}

private static long gcd(long a, long b)
{
    if (b == 0) {
        return a;
    }
    return gcd(b, a % b);
}
```