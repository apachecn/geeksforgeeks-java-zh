# 爪哇郎。Java 中的 Long.numberOfTrailingZeros()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-number of trailing zeros-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-numberoftrailingzeros-method-java-examples/)

**java . lang . long . numberoftrainingzeros()**是 Java 中的一个内置函数，它返回最低顺序设置位右边的尾随零位数。简单来说，它返回**(位置-1)** ，其中位置指的是从右侧开始的第一个设置位。如果数字不包含任何设置位(换句话说，如果数字为零)，它将返回 64。

**语法:**

```java
public static long numberOfTrailingZeros(long num)
Parameters:
num - the number passed 
Returns:
the number of trailing zeros after the lowest-order set bit

```

示例:

```java
Input :  8
Output : 3 
Explanation: Binary representation of 8 is 1000 
No of trailing zeros to the right of the lowest-order set
bit is 3\. 

Input : 191
Output : 0 

```

下面的程序说明了 Java . lang . long . numberoftrailingzeros()函数:

**程序 1:**

```java
// Java program that demonstrates the
// Long.numberOfTrailingZeros() function

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = 8;

        // returns the number of zero bits following the lowest-order
        // set bit
        System.out.println("Number of trailing zeros = "
                           + Long.numberOfTrailingZeros(l));

        // second example
        l = 25;
        System.out.println("Number of trailing zeros = "
                           + Long.numberOfTrailingZeros(l));
    }
}
```

输出:

```java
Number of trailing zeros = 3
Number of trailing zeros = 0

```

**程序 2:** 下面的程序演示了传递负数时函数的使用。

```java
// Java program that demonstrates the
// Long.numberOfTrailingZeros() function
// negative number
// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = -12;

        // returns the number of zero bits following the lowest-order
        // set bit
        System.out.println("Number of trailing zeros = "
                           + Long.numberOfTrailingZeros(l));
    }
}
```

输出:

```java
Number of trailing zeros = 2

```

当十进制字符串值作为参数传递时，它会返回一条错误消息。
**程序 3:** 当一个十进制值在参数中传递时。

```java
// Java program that demonstrates the
// Long.numberOfTrailingZeros() function
// decimal value as an argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // returns the number of zero bits following the lowest-order
        // set bit
        System.out.println("Number of trailing zeros = "
                           + Long.numberOfTrailingZeros(12.34));
    }
}
```

输出:

```java
prog.java:16: error: incompatible types: possible lossy conversion from double to long
      System.out.println("Number of trailing zeros = "+Long.numberOfTrailingZeros(12.34));

```

**程序 4:** 当一个字符串值在参数中传递时。

```java
// java program that demonstrates the
// Long.numberOfTrailingZeros() function
// string value as an argument

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // returns the number of zero bits following the lowest-order
        // set bit
        System.out.println("Number of trailing zeros = "
                           + Long.numberOfTrailingZeros("100"));
    }
}
```

输出:

```java
prog.java:15: error: incompatible types: String cannot be converted to long
      System.out.println("Number of trailing zeros = "+Long.numberOfTrailingZeros("100"));

```