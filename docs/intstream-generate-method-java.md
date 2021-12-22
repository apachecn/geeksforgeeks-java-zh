# Java 中的 IntStream generate()方法

> 原文:[https://www . geesforgeks . org/int stream-generate-method-Java/](https://www.geeksforgeeks.org/intstream-generate-method-java/)

**int stream generate(int suppliers s)**返回一个无限顺序无序流，其中每个元素都是由提供的**int supplier**(int-value 结果的供应商)生成的。这适用于生成恒定流、随机元素流等。

**语法:**

```java
static IntStream generate(IntSupplier s)

```

**参数:**

1.  **intstream** : original int value element sequence.
2.  **intsupplier** : the supplier of the int value element.
3.  **s** : the international supplier that generated the element.

**返回值:**一个新的无限顺序无序 IntStream。

**示例 1 :** 生成随机整数流。

```java
// Java code for IntStream.generate()
// to generate an infinite sequential
// unordered IntStream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // using IntStream.generate() method
        // to generate 7 random Integer values
        IntStream stream = IntStream.generate(()
                          -> { return (int)(Math.random() * 10000); });

        // Displaying the randomly generated values
        stream.limit(7).forEach(System.out::println);
    }
}
```

输出:

```java
4247
6827
2676
9129
3360
8718
7925

```