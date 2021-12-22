# Java 中的 IntStream sum()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-sum-Java/

**IntStream sum()** 返回此流中元素的总和。这是**减**的特例。IntStream sum()是一个 ***终端操作*** ，也就是说，它可能会遍历该流以产生结果或副作用。

**注:**约简操作(也称为折叠)取一系列输入元素，通过重复应用组合操作(如求一组数字的和或最大值)将它们组合成单个汇总结果。

**语法:**

```java
int sum()

```

**返回值:**函数返回该流中元素的总和。

**例 1 :**

```java
// Java code for IntStream.sum() to
// find the sum of elements in IntStream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, -2, -4);

        // Using IntStream.sum() to find
        // sum of elements in IntStream
        int sumOfElements = stream.sum();

        // Displaying the calculated sum
        System.out.println(sumOfElements);
    }
}
```

**Output:**

```java
6

```

**例 2 :**

```java
// Java code for IntStream.sum() to
// find the sum of elements
// divisible by 3 in given range
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Using IntStream.sum() to find
        // sum of elements dividible by 3
        // in given range
        int sumOfElements = IntStream.range(2, 10)
                           .filter(num -> num % 3 == 0)
                           .sum();

        // Displaying the calculated sum
        System.out.println(sumOfElements);
    }
}
```

**Output:**

```java
18

```