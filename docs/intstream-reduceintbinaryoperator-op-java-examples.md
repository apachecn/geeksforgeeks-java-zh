# Java 中的 int stream reduce(int binaryooperator op)示例

> 原文:[https://www . geesforgeks . org/int stream-reduce intbinaryoperator-op-Java-examples/](https://www.geeksforgeeks.org/intstream-reduceintbinaryoperator-op-java-examples/)

**int stream reduce(int binaryoperator op)**使用 ***关联*** 累加函数对该流的元素进行约简，并返回描述约简值的 OptionalInt(如果有)。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 **op** 是关联的:

```
(a op b) op c == a op (b op c)

```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
OptionalInt reduce(IntBinaryOperator op)

```

**参数:**

*   **OptionalInt :** 可能包含也可能不包含 Int 值的容器对象。如果存在一个值，is present()将返回 true，getAsInt()将返回该值。
*   **int binaryooperator:**对两个 int 值操作数进行运算并产生一个 int 值结果。
*   **op :** 用于组合两个值的关联无状态函数。

**返回值:**一个描述减少值(如果有)的选项。

**例 1 :**

```
// Java code for IntStream reduce
// (IntBinaryOperator op)
import java.util.OptionalInt;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 3, 4, 5, 6);

        // Using OptionalInt (a container object which
        // may or may not contain a non-null value)
        // Using IntStream reduce(IntBinaryOperator op)
        OptionalInt answer = stream.reduce(Integer::sum);

        // if the stream is empty, an empty
        // OptionalInt is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsInt());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
20

```

**例 2 :**

```
// Java code for IntStream reduce
// (IntBinaryOperator op)
import java.util.OptionalInt;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 3, 4, 5, 6);

        // Using OptionalInt (a container object which
        // may or may not contain a non-null value)
        // Using IntStream reduce(IntBinaryOperator op)
        OptionalInt answer = stream.reduce((a, b) -> (a * b));

        // if the stream is empty, an empty
        // OptionalInt is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsInt());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
720

```