# Java 中的 DoubleStream generate()方法

> 原文:[https://www . geesforgeks . org/double stream-generate-method-Java/](https://www.geeksforgeeks.org/doublestream-generate-method-java/)

**双流生成(双供应商)**返回一个无限顺序无序流，其中每个元素由提供的**双供应商**(双值结果的供应商)生成。这适用于生成恒定流、随机元素流等。

**语法:**

```
static DoubleStream generate(DoubleSupplier s)

```

**参数:**

1.  **Shuangliu: Original binary element sequence.**
***   **Dual supplier** : the supplier of dual value elements.*   **s** : the dual supplier that generated the element.**

****返回值:**一个新的无限顺序无序双流。**

****例 1 :** 生成随机双打流。**

```
// Java code for DoubleStream.generate()
// to generate an infinite sequential
// unordered DoubleStream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // using DoubleStream.generate() method
        // to generate 7 random Double values
        DoubleStream stream = DoubleStream.generate(()
           -> { return (double)(Math.random() * 10000); });

        // Displaying the randomly generated values
        stream.limit(7).forEach(System.out::println);
    }
}
```

****输出:**

```
2428.4470875214092
1339.9762523410686
302.44560518440267
9004.604086737152
3627.071411231598
2865.762726856176
4029.711939243109

```**