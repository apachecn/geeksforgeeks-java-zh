# Java 中的 LongStream reduce(longbinaryooperator op)

> 原文:[https://www . geeksforgeeks . org/longstream-reduce longbinaryooperator-op-Java/](https://www.geeksforgeeks.org/longstream-reducelongbinaryoperator-op-java/)

**LongStream reduce(LongBinaryOperator op)**使用 ***关联*** 累积函数对该流的元素执行缩减，并返回描述缩减值的选项龙(如果有)。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 **op** 是关联的:

```
(a op b) op c == a op (b op c)

```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
OptionalLong reduce(LongBinaryOperator op)

```

**参数:**

*   **选项龙:**可能包含也可能不包含长值的容器对象。如果存在一个值，is present()将返回 true，getAsLong()将返回该值。
*   **longbinaryooperator:**对两个长值操作数进行运算并产生长值结果的操作。
*   **op :** 用于组合两个值的关联无状态函数。

**返回值:**描述减少值的选项龙，如果有的话。

**例 1 :**

```
// Java code for LongStream reduce
// (LongBinaryOperator op)
import java.util.OptionalLong;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(9L, 10L, 11L, 12L);

        // Using OptionalLong (a container object which
        // may or may not contain a non-null value)
        // Using LongStream reduce(LongBinaryOperator op)
        OptionalLong answer = stream.reduce(Long::sum);

        // if the stream is empty, an empty
        // OptionalLong is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsLong());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
42

```

**例 2 :**

```
// Java code for LongStream reduce
// (LongBinaryOperator op)
import java.util.OptionalLong;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(9L, 10L, 11L, 12L);

        // Using OptionalLong (a container object which
        // may or may not contain a non-null value)
        // Using LongStream reduce(LongBinaryOperator op)
        OptionalLong answer = stream.reduce((a, b) -> 2 * (a * b));

        // if the stream is empty, an empty
        // OptionalLong is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsLong());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
95040

```