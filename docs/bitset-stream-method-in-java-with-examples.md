# Java 中的 BitSet 流()方法，示例

> 原文:[https://www . geesforgeks . org/bitset-stream-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bitset-stream-method-in-java-with-examples/)

Java BitSet 类的 stream()方法用于为 BitSet 中包含的每个位返回一个索引流。索引以递增的顺序返回。流的大小是 BitSet 的 set 状态的位数，等于[基数()](https://www.geeksforgeeks.org/java-bitset-cardinality/)方法返回的值。

**语法:**

```java
public IntStream stream()
```

**参数:**该方法不取任何参数。
**返回值:**该方法为位集中包含的每个位返回一个索引流。

以下程序说明了 java.util.BitSet.stream()方法的工作:
**程序 1:**

```java
// Java code to illustrate stream()
import java.util.*;
import java.util.stream.IntStream;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(10);
        init_bitset.set(20);
        init_bitset.set(30);
        init_bitset.set(40);
        init_bitset.set(50);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Creating an IntStream
        IntStream indice_Stream = init_bitset.stream();

        // Displaying the working
        System.out.println("The BitSet: " + init_bitset);
        System.out.println("The stream of indices: "
                           + indice_Stream);
        System.out.println("The size of the stream: "
                           + indice_Stream.count());
    }
}
```

**Output:**

```java
BitSet: {10, 20, 30, 40, 50}
The BitSet: {10, 20, 30, 40, 50}
The stream of indices: java.util.stream.IntPipeline$Head@4eec7777
The size of the stream: 5

```

**程序 2:**

```java
// Java code to illustrate stream()
import java.util.*;
import java.util.stream.IntStream;

public class BitSet_Demo {
    public static void main(String args[])
    {
        // Creating an empty BitSet
        BitSet init_bitset = new BitSet();

        // Use set() method to add elements into the Set
        init_bitset.set(40);
        init_bitset.set(25);
        init_bitset.set(31);
        init_bitset.set(100);
        init_bitset.set(121);
        init_bitset.set(400);
        init_bitset.set(2);
        init_bitset.set(15);
        init_bitset.set(106);
        init_bitset.set(55);

        // Displaying the BitSet
        System.out.println("BitSet: " + init_bitset);

        // Creating an IntStream
        IntStream indice_Stream = init_bitset.stream();

        // Displaying the working
        System.out.println("The BitSet: " + init_bitset);
        System.out.println("The stream of indices: "
                           + indice_Stream);
        System.out.println("The size of the stream: "
                           + indice_Stream.count());
    }
}
```

**Output:**

```java
BitSet: {2, 15, 25, 31, 40, 55, 100, 106, 121, 400}
The BitSet: {2, 15, 25, 31, 40, 55, 100, 106, 121, 400}
The stream of indices: java.util.stream.IntPipeline$Head@4eec7777
The size of the stream: 10

```