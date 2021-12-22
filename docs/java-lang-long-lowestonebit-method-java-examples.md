# 爪哇郎。Java 中的 Long.lowestOneBit()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-lowerstonebit-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-lowestonebit-method-java-examples/)

**java . lang . long . lowestonebit()**是 Java 中的一个内置方法，它首先将数字转换为二进制，然后查找出现在最低位置的第一个设置位，然后重置剩余的位，然后返回值。在简单语言中，如果一个数字的二进制表达式包含最少的一个设置位，它将从右-1 返回 2^(first 设置位位置。如果二进制表达式不包含任何设置位，则返回 0。

**语法:**

```
public static long lowestOneBit(long num)
Parameters:
num - the number passed 
Returns:
long value by only considering lowest 1 bit in the argument.
```

示例:

```
Input : 36 
Output : 4 
Explanation: Binary Representation = 0010 0100
It considers lowest bit(at 3) and now reset rest of the bits i.e. 0000 0100
so result = 0100 i.e. 4 or in simple terms, the first set 
bit position from right is at position 3, hence 2^2=4  

Input : 1032
Output : 8 

```

下面的程序说明了 java.lang.Long.lowestOneBit()函数:

**程序 1:**

```
// Java program that demonstrates the use of
// Long.lowestOneBit() function

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = 1032;

        // returns a long value with at most a single one-bit, in the position
        // of the lowest-order ("rightmost") one-bit in the specified int value.
        System.out.println("Lowest one bit = " + Long.lowestOneBit(l));

        l = 45;
        System.out.println("Lowest one bit = " + Long.lowestOneBit(l));
    }
}
```

输出:

```
Lowest one bit = 8
Lowest one bit = 1

```

**程序 2:** 下面的程序演示了传递负数时函数的使用。

```
// java program that demonstrates the use of
// Long.lowestOneBit() function
// negative number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = -12;

        // prints the binary of a negative expression
        System.out.println("Binary = " + Long.toBinaryString(l));

        // returns a long value with at most a single one-bit, in the position
        // of the lowest-order ("rightmost") one-bit in the specified int value.
        System.out.println("Lowest one bit = " + Long.lowestOneBit(l));
    }
}
```

输出:

```
Binary = 1111111111111111111111111111111111111111111111111111111111110100
Lowest one bit = 4

```

当十进制字符串值作为参数传递时，它会返回一条错误消息。

**程序 3:** 当一个十进制值在参数中传递时。

```
// java program that demonstrates the
// Long.lowestOneBit() function
// decimal value in argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("Lowest one bit = " + Long.lowestOneBit(12.34));
    }
}
```

输出:

```
prog.java:12: error: incompatible types: possible lossy conversion from double to long
      System.out.println("Lowest one bit = " + Long.lowestOneBit(12.34)); 

```

**程序 4:** 当一个字符串值在参数中传递时。

```
// java program that demonstrates the
// Long.lowestOneBit() function
// string value in argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("Lowest one bit = " + Long.lowestOneBit("12"));
    }
}
```

输出:

```
prog.java:12: error: incompatible types: String cannot be converted to long
      System.out.println("Lowest one bit = " + Long.lowestOneBit("12"));  

```