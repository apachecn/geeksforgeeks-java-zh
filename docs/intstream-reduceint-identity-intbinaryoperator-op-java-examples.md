# Java 中的 IntStream reduce(int identity，IntBinaryOperator op)示例

> 原文:[https://www . geesforgeks . org/int stream-reduce int-identity-intbinaryoperator-op-Java-examples/](https://www.geeksforgeeks.org/intstream-reduceint-identity-intbinaryoperator-op-java-examples/)

**IntStream reduce(int identity，IntBinaryOperator op)** 使用提供的标识值和关联累加函数对该流的元素执行约简，并返回约简后的值。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 **op** 是关联的:

```java
(a op b) op c == a op (b op c)

```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```java
int reduce(int identity,  IntBinaryOperator op)

```

**参数:**

*   **标识:**累加函数的标识值。
*   **int binaryooperator:**对两个 int 值操作数进行运算并产生一个 int 值结果。
*   **op :** 用于组合两个值的关联无状态函数。

**返回值:**还原的结果。

**例 1 :**

```java
// Java code for IntStream reduce
// (int identity, IntBinaryOperator op)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 3, 4, 5, 6);

        // Using IntStream reduce
        // (int identity, IntBinaryOperator op)
        int answer = stream.reduce(0, (num1, num2)
                                          -> (num1 + num2) * 2);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
176

```

**例 2 :**

```java
// Java code for IntStream reduce
// (int identity, IntBinaryOperator op)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(4, 10);

        // Using IntStream reduce
        // (int identity, IntBinaryOperator op)
        int answer = stream.reduce(0, (num1, num2)
                                          -> (num1 + num2) - 2 * (num1 - num2));

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
9

```