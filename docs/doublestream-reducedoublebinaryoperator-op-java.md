# Java 中的双流减少(double binaryoperator op)

> 原文:[https://www . geesforgeks . org/double stream-reduce double binaryoperator-op-Java/](https://www.geeksforgeeks.org/doublestream-reducedoublebinaryoperator-op-java/)

**双流缩减(双流操作符)**使用 ***关联*** 累积函数对该流的元素执行缩减，并返回描述缩减值的 OptionalDouble(如果有)。

一个**约简操作**或**折叠**取一个输入元素序列，并把它们组合成一个单一的汇总结果，比如求一组数字的和或最大值。如果满足以下条件，则运算符或函数 **op** 是关联的:

```java
(a op b) op c == a op (b op c)

```

这是一个**终端操作**，也就是说，它可能会遍历流以产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```java
OptionalDouble reduce(DoubleBinaryOperator op)

```

**参数:**

*   **optionalduble:**可能包含也可能不包含长值的容器对象。如果存在值，is present()将返回 true，getAsDouble()将返回该值。
*   **双二进制运算符:**对两个双值操作数进行运算并产生双值结果。
*   **op :** 用于组合两个值的关联无状态函数。

**返回值:**一个描述减少的值(如果有的话)的 OptionalDouble。

**例 1 :**

```java
// Java code for DoubleStream reduce
// (DoubleBinaryOperator op)
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3, 3.4, 4.5);

        // Using OptionalDouble (a container object which
        // may or may not contain a non-null value)
        // Using DoubleStream reduce(DoubleBinaryOperator op)
        OptionalDouble answer = stream.reduce(Double::sum);

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
        else {
            System.out.println("Stream is empty");
        }
    }
}
```

输出:

```java
11.4

```

**例 2 :**

```java
// Java code for DoubleStream reduce
// (DoubleBinaryOperator op)
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3, 3.4, 4.5);

        // Using OptionalDouble (a container object which
        // may or may not contain a non-null value)
        // Using DoubleStream reduce(DoubleBinaryOperator op)
        OptionalDouble answer = stream.reduce((a, b)
                                  -> (a * b) * (a * b));

        // if the stream is empty, an empty
        // OptionalDouble is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsDouble());
        }
        else {
            System.out.println("Stream is empty");
        }
    }
}
```

输出:

```java
9111992.471343633

```