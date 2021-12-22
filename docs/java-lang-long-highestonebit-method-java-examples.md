# 爪哇郎。Java 中的 Long.highestOneBit()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-highestonebit-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-highestonebit-method-java-examples/)

**java . lang . long . higheestonebit()**是 Java 中的一个内置方法，它首先将数字转换为二进制，然后从左边查找第一个设置位，然后重置其余位，然后返回值。在简单语言中，如果一个数字的二进制表达式包含最少的一个设置位，它将从右-1 返回 2^(last 设置位位置。如果二进制表达式不包含任何设置位，则返回 0。

**语法:**

```java
public static long highestOneBit(long num)
Parameters:
num - the number passed 
Returns:
long value by only considering highest 1 bit in the argument.
```

示例:

```java
Input : 9 
Output : 8
Explanation: Binary Representation = 1001
It considers highest bit(at 4th from right) and now
reset rest of the bits i.e. 1000
so result = 1000 i.e. 8 or in simple terms, the last set 
bit position from right is at position 4, hence 2^3=8

Input : 45
Output : 32

```

下面的程序说明了 Java . lang . long . higheestonebit()函数:

**程序 1:**

```java
// Java program that demonstrates the use of
// Long.highestOneBit() function

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = 9;

        // returns a long value with at most a
        // single one-bit, in the position
        // of the highest-order ("rightmost")
        // one-bit in the specified long value.
        System.out.println("highest one bit = " + Long.highestOneBit(l));

        l = 45;
        System.out.println("highest one bit = " + Long.highestOneBit(l));
    }
}
```

输出:

```java
highest one bit = 8
highest one bit = 32

```

**注意:**负数的最高位在任何情况下都是相同的，因此不管是哪个数字，每个负数的输出都是相同的。

**程序 2:** 下面的程序演示了传递负数时函数的使用。

```java
// java program that demonstrates the use of
// Long.highestOneBit() function
// negative number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = -15;

        // prints the binary of a negative expression
        System.out.println("Binary = " + Long.toBinaryString(l));

        // returns a long value with at
        // most a single one-bit, in the position
        // of the highest-order ("rightmost")
        // one-bit in the specified int value.
        System.out.println("Highest one bit = " + Long.highestOneBit(l));
    }
}
```

输出:

```java
Binary = 1111111111111111111111111111111111111111111111111111111111110001
Highest one bit = -9223372036854775808

```

当十进制字符串值作为参数传递时，它会返回一条错误消息。
**程序 3:** 当一个十进制值在参数中传递时。

```java
// java program that demonstrates the
// Long.highestOneBit() function
// decimal value in argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("highest one bit = " + Long.highestOneBit(12.34));
    }
}
```

输出:

```java
prog.java:13: error: incompatible types: possible lossy conversion from double to long
        System.out.println("highest one bit = " + Long.highestOneBit(12.34));

```

**程序 3:** 当一个字符串值在参数中传递时。

```java
// java program that demonstrates the
// Long.highestOneBit() function
// string value in argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("highest one bit = " + Long.highestOneBit("12"));
    }
}
```

输出:

```java
prog.java:13: error: incompatible types: String cannot be converted to long
        System.out.println("highest one bit = " + Long.highestOneBit("12"));

```