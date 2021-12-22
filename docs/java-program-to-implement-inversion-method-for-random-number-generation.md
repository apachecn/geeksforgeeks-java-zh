# 实现随机数生成反演方法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-求逆-随机数生成方法/](https://www.geeksforgeeks.org/java-program-to-implement-inversion-method-for-random-number-generation/)

这里我们将学习 java 中随机数生成的逆序方法。所以基本上我们将说明两种方法，如下所示:

1.  排列数组中的元素
2.  使用 Collection.shuffle()方法

这里的重要方法就是 setSeed()。它用于通过使用单个长种子的随机数生成器的随机类集的 *setSeed()方法*来设置种子。

**语法:**

```java
setSeed()
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to implement inversion for random number
// generation

// Importing Random class from java.util package
import java.util.Random;

// Main class
class GFG {

    // Method 1
    // To calculate seed value
    public static long calcSeed(long nextLong)
    {

        // Declaring and initializing variables
        // Custom initialization
        final long x = 0x5DEECE66DL;
        final long xinv = 0xdfe05bcb1365L;
        final long y = 0xBL;
        final long mask = ((1L << 48) - 1);

        long a = nextLong >>> 32;
        long b = nextLong & ((1L << 32) - 1);

        if ((b & 0x80000000) != 0)
            a++;

        // b had a sign bit, so we need to restore a
        long q = ((b << 16) - y - (a << 16) * x) & mask;

        for (long k = 0; k <= 5; k++) {

            long rem = (x - (q + (k << 48))) % x;
            long d = (rem + x) % x; // force positive

            if (d < 65536) {

                long c = ((q + d) * xinv) & mask;

                if (c < 65536) {
                    return ((((a << 16) + c) - y) * xinv)
                        & mask;
                }
            }
        }

        // Throws keyword pops up the message
        // as exception is encountered during runtime
        throw new RuntimeException("Failed!!");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Setting a random number in main() method by
        // creating an object of Random class
        Random r = new Random();

        // Getting the next random number
        long next = r.nextLong();

        // Print and display the next long value
        System.out.println("Next long value: " + next);

        // Calling method 1
        long seed = calcSeed(next);

        // Print and display the ssed value
        System.out.println("Seed " + seed);

        // setSeed mangles the input,
        // so demangling here to get the right output by
        // creating another object of Random class
        Random r2 = new Random((seed ^ 0x5DEECE66DL)
                               & ((1L << 48) - 1));

        // Printing the next ssed value
        // using nextLong() method
        System.out.println("Next long value from seed: "
                           + r2.nextLong());
    }
}
```

**Output**

```java
Next long value: 3738641717178320652
Seed 158514749661962
Next long value from seed: 3738641717178320652
```

**输出解释:**

Random 使用一个 48 位种子和一个线性同余生成器。这些不是密码安全的生成器，因为状态大小很小，而且输出也不是随机的(许多生成器在某些位上会显示出很小的周期长度，这意味着即使其他位看起来是随机的，这些位也可以很容易地预测)。

Random 的种子更新如下:

```java
nextseed = (seed * 0x5DEECE66DL + 0xBL) & ((1L << 48) - 1)
```

这是一个非常简单的函数，如果你通过计算知道种子的所有位，它可以被反转

```java
seed = ((nextseed - 0xBL) * 0xdfe05bcb1365L) & ((1L << 48) - 1)
```

因为 0x5deece 66dl * 0xdfe 05 BCB 1365 l = 1 mod 248。这样，任何时间点的单个种子值都足以恢复所有过去和未来的种子。

然而，Random 没有揭示整个种子的功能，所以我们必须聪明一点。

现在，很明显，使用 48 位种子，你必须观察至少 48 位的输出，否则你显然没有内射(因此是可逆的)函数可以使用。我们运气好:nextLong 返回((long)(next(32))< < 32)+next(32)；，所以它产生 64 位的输出(比我们需要的多)。事实上，我们也许可以凑合使用 nextDouble(它产生 53 位)，或者只是重复调用任何其他函数。请注意，由于种子的大小有限，这些函数输出的唯一值不能超过 248 个(因此，例如，有 264-248 个长值，nextLong 永远不会产生)。

让我们具体看看 nextLong。它返回一个数字(a << 32) + b，其中 a 和 b 都是 32 位的量。在调用 nextLong 之前，让我们成为种子。然后，让 t = s * 0x5DEECE66DL + 0xBL，这样 a 是 t 的高 32 位，让 u = t * 0x5DEECE66DL + 0xBL，这样 b 是 u 的高 32 位，让 c 和 d 分别是 t 和 u 的低 16 位。

请注意，由于 c 和 d 是 16 位的量，我们可以直接用暴力**–**强制它们(因为我们只需要一个)并完成它。这相当便宜，因为 216 只有 65536 英镑——对一台电脑来说很小。但是让我们更聪明一点，看看是否有更快的方法。

我们有(b < < 16)+d =((a < < 16)+c)* 0x5deece 66dl+11。因此，做一些代数运算，我们得到(b < < 16–11 –( a < < 16)* 0x5deece 66dl = c * 0x5deece 66dl–d，mod 248。由于 c 和 d 都是 16 位量，c*0x5DEECE66DL 最多有 51 位。这意味着

```java
(b << 16) - 11 - (a << 16)*0x5DEECE66DL + (k<<48)
```

对于某些 k，最多等于 c * 0x5deece 66dl–d 6。(有更复杂的方法来计算 c 和 d，但是因为 k 上的边界非常小，所以更容易使用暴力)。

我们可以测试 k 的所有可能值，直到我们得到一个取反余数 mod 0x5DEECE66DL 为 16 位的值(再次为 mod 248)，这样我们就可以恢复 t 和 u 的较低的 16 位。此时，我们有一个完整的种子，因此我们可以使用第一个等式找到未来的种子，或者使用第二个等式找到过去的种子。如下例所示:

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement Inversion Method for
// Random Number Generation

// Importing required classes 
import java.util.Arrays;
import java.util.Random;
import javax.sql.RowSetEvent;
import javax.sql.RowSetListener;
import javax.sql.rowset.JdbcRowSet;
import javax.sql.rowset.RowSetProvider;

// Main class
// To test random reverse
class GFG {

    // The secret seed that we want to find
    private static long SEED = 782634283105L;

    // Number of random numbers to be generated
    private static int NUM_GEN = 5;

    // Method 1
    private static int[] genNum(long seed)
    {
        Random rand = new Random(seed);
        int arr[] = new int[NUM_GEN];
        for (int i = 0; i < arr.length; i++) {
            arr[i] = rand.nextInt();
        }

        return arr;
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {

        int arr[] = genNum(SEED);
        System.out.println(Arrays.toString(arr));

        Long result = reverse(arr);

        if (result != null) {
            System.out.println(
                Arrays.toString(genNum(result)));
        }
        else {
            System.out.println("Seed not found");
        }
    }

    // Method 3
    private static long combine(int rand, int suffix)
    {
        return (unsignedIntToLong(rand) << 16)
            | (suffix & ((1L << 16) - 1));
    }

    // Method 4
    private static long unsignedIntToLong(int num)
    {
        return num & ((1L << 32) - 1);
    }

    // Method 5
    // To find the seed of a sequence of
    // integer, generated by nextInt() Can be easily
    // modified to find the seed of a sequence of long,
    // generated by nextLong()
    private static Long reverse(int arr[])
    {

        // Need at least 2 numbers.
        assert (arr.length > 1);

        int end = arr.length - 1;

        // Brute force lower 16 bits, then compare
        // upper 32 bit of the previous seed generated
        // to the previous number.
        for (int i = 0; i < (1 << 16); i++) {

            long candidateSeed = combine(arr[end], i);
            long previousSeed
                = getPreviousSeed(candidateSeed);

            if ((previousSeed >>> 16)
                == unsignedIntToLong(arr[end - 1])) {

                System.out.println("Testing seed: "
                                   + previousSeed + " --> "
                                   + candidateSeed);

                for (int j = end - 1; j >= 0; j--) {
                    candidateSeed = previousSeed;
                    previousSeed
                        = getPreviousSeed(candidateSeed);

                    if (j > 0
                        && (previousSeed >>> 16)
                               == unsignedIntToLong(
                                   arr[j - 1])) {

                        System.out.println(
                            "Verifying: " + previousSeed
                            + " --> " + candidateSeed);
                    }
                    else if (j == 0) {

                        // The XOR is done when the seed is
                        // set, need to reverse it
                        System.out.println(
                            "Seed found: "
                            + (previousSeed ^ MULTIPLIER));

                        return previousSeed ^ MULTIPLIER;
                    }
                    else {
                        // Print statement
                        System.out.println("Failed");

                        // break keyword
                        break;
                    }
                }
            }
        }

        return null;
    }

    private static long ADDEND = 0xBL;
    private static long MULTIPLIER = 0x5DEECE66DL;

    // Method 6
    private static long getPreviousSeed(long currentSeed)
    {

        long seed = currentSeed;

        // Reverse the addend from the seed
        // Reversing the addend
        seed -= ADDEND;

        long result = 0;

        // Iterating through the seeds bits
        for (int i = 0; i < 48; i++) {

            long mask = 1L << i;
            // find the next bit
            long bit = seed & mask;
            // add it to the result

            result |= bit;

            if (bit == mask) {
                // if the bit was 1, subtract its effects
                // from the seed
                seed -= MULTIPLIER << i;
            }
        }

        return result & ((1L << 48) - 1);
    }
}
```

**输出:**

```java
[826100673, 702667566, 238146028, -1525439028, -133372456]
Testing seed: 181503804585936 --> 272734279476123
Verifying: 15607138131897 --> 181503804585936
Verifying: 46050021665190 --> 15607138131897
Verifying: 54139333749543 --> 46050021665190
Seed found: 782634283105
[826100673, 702667566, 238146028, -1525439028, -133372456]
```

**输出解释:**程序将蛮力作用在下方 16

*   -由 nextInt()丢弃的位，使用 James Roper 在博客中提供的算法找到前一个种子，然后检查 48 位种子的**高 32 位是否与前一个数字相同。我们至少需要 2 个整数来导出前一个种子。否则，前一个种子将有 216 种可能性，在我们至少还有一个数字之前，它们都是同等有效的。**
*   **它可以很容易地扩展为 nextLong()，1 个长数字就足以找到种子，因为由于它的生成方式，我们在一个长中有 2 个种子的上部 32 位。**

> ****注意:**有些情况下，结果与您在 seed 变量中设置为秘密种子的结果不一样。如果您设置为秘密种子的数字超过 48 位(这是内部用于生成随机数的位数)，那么在 setSeed()方法中将删除 64 位长的高 16 位。在这种情况下，返回的结果将不会与您最初设置的结果相同，很可能较低的 48 位会相同。**