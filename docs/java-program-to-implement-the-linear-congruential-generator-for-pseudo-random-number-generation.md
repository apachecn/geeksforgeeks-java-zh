# 实现用于伪随机数生成的线性同余生成器的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-实现伪随机数生成的线性同余生成器/](https://www.geeksforgeeks.org/java-program-to-implement-the-linear-congruential-generator-for-pseudo-random-number-generation/)

**线性同余法**是一类伪随机数发生器(PRNG)算法，用于生成特定范围内的类随机数序列。这种方法可以定义为:

> **x<sub>【I+1】</sub>= ax<sub>【I】</sub>+c mod m**
> 
> 哪里，
> 
> x，是伪随机数的序列
> 
> m，(> 0)为模数
> 
> a，(0，m)乘数
> 
> c，(0，m)增量
> 
> X0，[0，m]–称为种子的序列初始值

> **注意:** m、a、c、X0 要适当选择，得到一个几乎等于 m 的周期。

*   对于 a = 1，它将是加法同余法。
*   对于 c = 0，将是乘法同余法。

**进场:**

*   选择种子值 X0、模数参数 m、乘数项 a 和增量项 c
*   初始化生成随机数所需的数量(比如，一个整数变量 noOfRandomNums)。
*   定义存储以保持生成的随机数(这里考虑的是矢量)的大小不变。
*   用种子值初始化向量的第 0 个索引。
*   对于其余的索引，遵循线性同余法生成随机数。

**randomNums[i] = （（randomNums[i – 1] * a） + c） % m**

*   最后，返回随机数。

**以下是上述方法的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of the above approach
import java.util.*;

class GFG {

    // Function to generate random numbers
    static void lcm(int seed, int mod, int multiplier,
                    int inc, int[] randomNums,
                    int noOfRandomNum)
    {

        // Initialize the seed state
        randomNums[0] = seed;

        // Traverse to generate required
        // numbers of random numbers
        for (int i = 1; i < noOfRandomNum; i++) {

            // Follow the linear congruential method
            randomNums[i]
                = ((randomNums[i - 1] * multiplier) + inc)
                  % m;
        }
    }

    // Driver code
    public static void main(String[] args)
    {

        // Seed value
        int seed = 5;

        // Modulus parameter
        int mod = 7;

        // Multiplier term
        int multiplier = 3;

        // Increment term
        int inc = 3;

        // Number of Random numbers
        // to be generated
        int noOfRandomNum = 10;

        // To store random numbers
        int[] randomNums = new int[noOfRandomNum];

        // Function Call
        lcm(seed, mod, multiplier, inc, randomNums,
            noOfRandomNum);

        // Print the generated random numbers
        for (int i = 0; i < noOfRandomNum; i++) {
            System.out.print(randomNums[i] + " ");
        }
    }
}
```

**Output**

```
5 4 1 6 0 3 5 4 1 6
```

伪的字面意思是假的或想象的。这些随机数被称为伪随机数，因为使用了一些已知的算术过程来生成它们。即使生成的序列形成一个模式，因此生成的数字看起来是随机的，但可能不是真正随机的。