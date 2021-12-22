# 爪哇郎。Java 中的 Long.numberOfLeadingZeros()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-number of leading zeros-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-numberofleadingzeros-method-java-examples/)

**java . lang . long . number of leading zeros()**是 Java 中的一个内置函数，它返回最高阶集合位左边的前导零位数。简单来说，它返回 **(64 位)**，其中位置指的是从右侧开始的最高阶设置位。如果数字不包含任何设置位(换句话说，如果数字为零)，它将返回 64。

**语法:**

```
public static long numberOfLeadingZeros(long num)
Parameters:
num - the number passed 
Returns:
the number of leading zeros before the highest-order set bit

```

示例:

```
Input : 8
Output : 60
Explanation: Binary representation of 8 is 1000 
No of leading zeros to the left of the highest-order set
bit is 60\. 

Input : 25
Output : 59

```

下面的程序说明了 Java . lang . long . numberofleading zerows()函数:

**程序 1:**

```
// Java program that demonstrates the
// Long.numberOfLeadingZeros() function

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = 8;

        // returns the number of zero bits before the highest-order
        // set bit
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros(l));

        // second example
        l = 25;
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros(l));
    }
}
```

输出:

```
Number of leading zeros = 60
Number of leading zeros = 59

```

**注意:**如果是负数，每个数字都会有 0 个前导零。

**程序 2:** 下面的程序演示了传递负数时函数的使用。

```
// Java program that demonstrates the
// Long.numberOfLeadingZeros() function
// negative number
// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = -12;

        // returns the number of zero bits before the highest-order
        // set bit
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros(l));

        l = -100;
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros(l));
    }
}
```

输出:

```
Number of leading zeros = 0
Number of leading zeros = 0

```

**程序 3:** 当一个十进制字符串值作为参数传递时，它会返回一条错误消息。

```
// Java program that demonstrates the
// Long.numberOfLeadingZeros() function
// decimal number
// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // returns the number of zero bits before the highest-order
        // set bit
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros(10.45));
    }
}
```

输出:

```
prog.java:16: error: incompatible types: possible lossy conversion from double to long
                           + Long.numberOfLeadingZeros(10.45));
```

**程序 4:** 当一个字符串值在参数中传递时。

```
// Java program that demonstrates the
// Long.numberOfLeadingZeros() function
// string number
// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        // returns the number of zero bits before the highest-order
        // set bit
        System.out.println("Number of leading zeros = "
                           + Long.numberOfLeadingZeros("10"));
    }
}
```

输出:

```
prog.java:16: error: incompatible types: String cannot be converted to long
                           + Long.numberOfLeadingZeros("10"));
```