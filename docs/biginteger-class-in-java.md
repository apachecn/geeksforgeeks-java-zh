# Java 中的 BigInteger 类

> 原文:[https://www.geeksforgeeks.org/biginteger-class-in-java/](https://www.geeksforgeeks.org/biginteger-class-in-java/)

BigInteger 类用于数学运算，它涉及非常大的整数计算，超出了所有可用的原始数据类型的限制。

这样，BigInteger 类由于其庞大的方法库而非常便于使用，并且在竞争性编程中也大量使用。
下面给出了一个简单的原始算术语句列表，以及它在 BigInteger 对象方面的类似语句。

**示例:**

```
int a, b;                
BigInteger A, B; 
```

初始化如下****:****

```
a = 54;
b = 23;
```

```
A  = BigInteger.valueOf(54);
B  = BigInteger.valueOf(37); 
```

**对于以字符串形式提供的整数，您可以按如下方式初始化它们:**

```
A  = new BigInteger(“54”);
B  = new BigInteger(“123456789123456789”); 
```

**为了便于初始化，在 BigInteger 类中还定义了一些常量，如下所示:**

```
A = BigInteger.ONE;
// Other than this, available constant are BigInteger.ZERO 
// and BigInteger.TEN 
```

**数学运算如下:**

```
int c = a + b;
BigInteger C = A.add(B); 
```

**其他类似的函数是减法()，乘法()，除法()，余数()，但是所有这些函数都以 BigInteger 作为参数，所以如果我们想用整数或字符串进行此操作，请在将它们传递给函数之前将其转换为 BigInteger，如下所示:**

```
String str = “123456789”;
BigInteger C = A.add(new BigInteger(str));
int val  = 123456789;
BigInteger C = A.add(BigInteger.valueOf(val)); 
```

**从 BigInteger 中提取值如下:**

```
int x   =  A.intValue();   // value should be in limit of int x
long y   = A.longValue();  // value should be in limit of long y
String z = A.toString(); 
```

**对比**

```
if (a < b) {}         // For primitive int
if (A.compareTo(B) < 0)  {} // For BigInteger 
```

**实际比较根据值返回-1(小于)、0(等于)、1(大于)。为了平等，我们还可以使用:**

```
if (A.equals(B)) {}  // A is equal to B 
```

### ****大整数类的方法****

<figure class="table">

| 方法 | 已执行的操作 |
| --- | --- |
| add(大整数 val) | 返回一个 BigInteger，其值为(this + val)。 |
| [**【ABS()**](https://www.geeksforgeeks.org/biginteger-abs-method-in-java/) | 返回一个大整数，其值是该大整数的绝对值。 |
| [和(大整数 val)](https://www.geeksforgeeks.org/biginteger-and-method-in-java/) | 返回一个值为(this & val)的大整数。 |
| and not(大整数 val | 返回一个 BigInteger，其值为(此为& ~val)。 |
| [bitCount()](https://www.geeksforgeeks.org/biginteger-bitcount-method-in-java/) | 返回这个大整数的二进制补码表示中与其符号位不同的位数。 |
| [比特长度()](https://www.geeksforgeeks.org/biginteger-bitlength-method-in-java/) | 返回此 BigInteger 的最小二进制补码表示中的位数，不包括符号位。 |
| [字节值精确()](https://www.geeksforgeeks.org/java-8-biginteger-bytevalueexact-method-with-examples/) | 将此 BigInteger 转换为字节，检查丢失的信息。 |
| [clearBit(int n)](https://www.geeksforgeeks.org/biginteger-clearbit-method-in-java/) | 返回一个大整数，其值与指定位清零后的大整数相等。 |
| [分享(BigInteger val)](https://www.geeksforgeeks.org/biginteger-compareto-method-in-java/) | 将此大整数与指定的大整数进行比较。 |
| 除法(BigInteger val) | 返回一个 BigInteger，其值为(this / val)。 |
| [除数(BigInteger val)](https://www.geeksforgeeks.org/java-8-biginteger-divideandremainder-method-with-examples/) | 返回一个由两个大整数组成的数组，包含(this / val)后跟(this % val)。 |
| [双值()](https://www.geeksforgeeks.org/biginteger-doublevalue-method-in-java/) | 将此 BigInteger 转换为双精度值。 |
| [等于(对象 x)](https://www.geeksforgeeks.org/biginteger-equals-method-in-java/) | 将此大整数与指定的对象进行相等比较。 |
| [翻转位(int n)](https://www.geeksforgeeks.org/biginteger-flipbit-method-in-java/) | 返回一个大整数，其值与指定位翻转后的大整数相等。 |
| [浮点值（）](https://www.geeksforgeeks.org/biginteger-floatvalue-method-in-java/) | 将此 BigInteger 转换为浮点数。 |
| gcd(大整数 val) | 返回一个 BigInteger，其值是 abs(this)和 abs(val)的最大公约数。 |
| [get time bit()](https://www.geeksforgeeks.org/biginteger-getlowestsetbit-method-in-java/) | 返回此 BigInteger 中最右边(最低阶)一位的索引(最右边一位右边的零位数)。 |
| hashCode() | 返回此 BigInteger 的哈希代码。 |
| [整数值（）](https://www.geeksforgeeks.org/biginteger-intvalue-method-in-java/) | 将此 BigInteger 转换为整数。 |
| [intValueExact()](https://www.geeksforgeeks.org/biginteger-intvalueexact-method-in-java-with-examples/) | 将此 BigInteger 转换为 int，检查丢失的信息。 |
| int certainty(内部确定性) | 如果这个大整数可能是质数，则返回真；如果它肯定是复合整数，则返回假。 |
| [长值（）](https://www.geeksforgeeks.org/biginteger-longvalue-method-in-java/) | 将此 BigInteger 转换为长整型。 |
| [longValueExact()](https://www.geeksforgeeks.org/java-8-biginteger-longvalueexact-method-with-examples/) | 将此 BigInteger 转换为长整型，检查丢失的信息。 |
| [最大值(BigInteger val)](https://www.geeksforgeeks.org/biginteger-max-and-min-methods-in-java/) | 返回这个 BigInteger 和 val 的最大值。 |
| min(big integer val | 返回这个 BigInteger 和 val 的最小值。 |
| [修改(BigInteger m](https://www.geeksforgeeks.org/biginteger-mod-method-in-java/) | 返回一个 BigInteger，其值为(此 mod m)。 |
| [修改(BigInteger m)](https://www.geeksforgeeks.org/java-math-biginteger-modinverse-method-in-java/) | 返回一个 BigInteger，其值为(此值为-1 mod m)。 |
| [modPow(BigInteger 指数，BigInteger m](https://www.geeksforgeeks.org/biginteger-modpow-method-in-java/) | 返回一个 BigInteger，其值为(this index mod m)。 |
| 倍数(BigInteger val) | 返回一个值为(this * val)的 BigInteger。 |
| [否定()](https://www.geeksforgeeks.org/biginteger-negate-method-in-java/) | 返回一个 BigInteger，其值为(-this)。 |
| 下一个概率犯罪() | 返回第一个大于这个可能是质数的大整数。 |
| [不是()](https://www.geeksforgeeks.org/biginteger-not-method-in-java/) | 返回一个值为(~this)的 BigInteger。 |
| [或【big integer val】](https://www.geeksforgeeks.org/biginteger-or-method-in-java/) | 返回一个 BigInteger，其值为(this &#124; val)。 |
| [幂(int 指数)](https://www.geeksforgeeks.org/biginteger-pow-method-in-java/) | 返回一个大整数，其值为(this index)。 |
| [概率素(int bitLength，Random rnd)](https://www.geeksforgeeks.org/java-math-biginteger-probableprime-method-in-java/) | 返回一个可能是质数的正整数，具有指定的位长度。 |
| [残馀(BigInteger val)](https://www.geeksforgeeks.org/biginteger-remainder-method-in-java/) | 返回一个 BigInteger，其值为(此为% val)。 |
| [七位元(int n)](https://www.geeksforgeeks.org/biginteger-setbit-method-in-java/) | 返回一个大整数，该大整数的值与设置了指定位的大整数相等。 |
| [移位(int n)](https://www.geeksforgeeks.org/biginteger-shiftleft-method-in-java/) | 返回一个 BigInteger，其值为(这是< < n)。 |
| [shiftRight(int n)](https://www.geeksforgeeks.org/biginteger-shiftright-method-in-java/) | 返回一个 BigInteger，其值为(this >> n)。 |
| [短值精确()](https://www.geeksforgeeks.org/java-8-biginteger-shortvalueexact-method-with-examples/) | 将此 BigInteger 转换为短整型，检查丢失的信息。 |
| 符号() | 返回这个 BigInteger 的符号函数。 |
| [sqrt()](https://www.geeksforgeeks.org/biginteger-sqrt-method-in-java/) | 返回此 BigInteger 的整数平方根。 |
| sqrtandremaineder_) | 返回一个由两个大整数组成的数组，分别包含这个的整数平方根 s 和它的余数 this–s * s。 |
| 减(BigInteger val) | 返回一个 BigInteger，其值为(this–val)。 |
| [测试(int n)](https://www.geeksforgeeks.org/biginteger-testbit-method-in-java/) | 当且仅当指定位被置位时，返回真。 |
| [toByteArray（）](https://www.geeksforgeeks.org/biginteger-tobytearray-method-in-java/) | 返回一个字节数组，其中包含此 BigInteger 的二进制补码表示。 |
| [toString()](https://www.geeksforgeeks.org/biginteger-tostring-method-in-java/) | 返回此大整数的十进制字符串表示形式。 |
| [toString(int 基数)](https://www.geeksforgeeks.org/biginteger-tostring-method-in-java/) | 以给定的基数返回此 BigInteger 的字符串表示形式。 |
| [valueOf(long val)](https://www.geeksforgeeks.org/biginteger-valueof-method-in-java/) | 返回一个 BigInteger，其值等于指定长整型的值。 |
| [xor(BigInteger val)](https://www.geeksforgeeks.org/biginteger-xor-method-in-java/) | 返回一个大整数，其值为(此^值)。 |

</figure>

**插图:**

**阶乘 100 包含 158 位数字，因此我们无法将其存储在任何可用的原始数据类型中。我们可以在其中存储任意大的整数。范围的上限没有理论上的限制，因为内存是动态分配的，但实际上由于内存有限，您可以存储一个整数。MAX_VALUE 其中足以存储大部分大值的位数。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to find large factorials using BigInteger
import java.math.BigInteger;
import java.util.Scanner;

public class Example
{
    // Returns Factorial of N
    static BigInteger factorial(int N)
    {
        // Initialize result
        BigInteger f = new BigInteger("1"); // Or BigInteger.ONE

        // Multiply f with 2, 3, ...N
        for (int i = 2; i <= N; i++)
            f = f.multiply(BigInteger.valueOf(i));

        return f;
    }

    // Driver method
    public static void main(String args[]) throws Exception
    {
        int N = 20;
        System.out.println(factorial(N));
    }
}
```

****输出:****

```
2432902008176640000
```

> ****提示:**如果一定要用 C++写上面的程序，那就太大太复杂了，可以看看[大数阶乘](https://www.geeksforgeeks.org/factorial-large-number/)。**

**所以在了解了 BigInteger 类的函数的上述知识之后，我们可以很容易地解决很多复杂的问题，但是请记住，由于 BigInteger 类在内部使用整数数组进行处理，对 BigInteger 对象的操作不如对 big integer 上正在添加函数的原语的操作快，并且不会占用恒定的时间，它所占用的时间与 big integer 的长度成正比，因此程序的复杂性也会相应地发生变化。**

**本文由乌卡什·特里维迪供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**

****必读:****

*   **[Java 中的大斐波那契数](https://www.geeksforgeeks.org/large-fibonacci-numbers-java/)**
*   **[BigInteger 类也提供了质数](https://www.geeksforgeeks.org/quick-ways-to-check-for-prime-and-find-next-prime-in-java/)的快速方法。**