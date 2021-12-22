# Java 中的 LongStream generate()方法

> 原文:[https://www . geesforgeks . org/longstream-generate-method-Java/](https://www.geeksforgeeks.org/longstream-generate-method-java/)

**LongStream generate(LongSupplier s)**返回一个无限顺序无序流，其中每个元素都是由提供的 **LongSupplier** (长值结果的提供者)生成的。这适用于生成恒定流、随机元素流等。

**语法:**

```
static LongStream generate(LongSupplier s)

```

**参数:**

1.  **longstream** : the original long-value element sequence.
2.  **Long Supplier** : the supplier of long-value elements.
3.  **s** : the long supplier that generated the element.

**返回值:**一个新的无限顺序无序 LongStream。

**例 1 :**

```
// Java code for LongStream.generate()
// to generate an infinite sequential
// unordered LongStream
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // using LongStream.generate() method
        // to generate 7 random Integer values
        LongStream stream = LongStream.generate(()
               -> { return (long)(Math.random() * 10000); });

        // Displaying the randomly generated values
        stream.limit(7).forEach(System.out::println);
    }
}
```

输出:

```
4377
6200
9920
6015
7879
7887
8792

```