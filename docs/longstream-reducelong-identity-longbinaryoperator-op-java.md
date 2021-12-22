# Java 中的 LongStream reduce(长标识，LongBinaryOperator op)示例

> 原文:[https://www . geesforgeks . org/longstream-reduce long-identity-longbinaryooperator-op-Java/](https://www.geeksforgeeks.org/longstream-reducelong-identity-longbinaryoperator-op-java/)

**LongStream reduce(long identity，LongBinaryOperator op)** 使用提供的标识值和关联累加函数，对该流的元素执行约简，并返回约简后的值。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 **op** 是关联的:

```java
(a op b) op c == a op (b op c)

```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```java
long reduce(long identity,  LongBinaryOperator op)

```

**参数:**

*   **标识:**累加函数的标识值。
*   **longbinaryooperator:**对两个长值操作数进行运算并产生长值结果的操作。
*   **op :** 用于组合两个值的关联无状态函数。

**返回值:**还原的结果。

**例 1 :**

```java
// Java code for LongStream reduce
// (long identity, LongBinaryOperator op)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(1L, 3L, 5L, 7L, 9L);

        // Using LongStream reduce
        // (long identity, LongBinaryOperator op)
        long answer = stream.reduce(0, (num1, num2)
                                           -> (num1 + num2));

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
25

```

**例 2 :**

```java
// Java code for LongStream reduce
// (long identity, LongBinaryOperator op)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.range(3L, 7L);

        // Using LongStream reduce
        // (long identity, LongBinaryOperator op)
        long answer = stream.reduce(0, (num1, num2)
                                           -> (num1 * num2) - (num1 - num2));

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
291

```