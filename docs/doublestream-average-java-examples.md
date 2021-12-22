# Java 中的双流平均值()，示例

> 原文:[https://www . geesforgeks . org/double stream-average-Java-examples/](https://www.geeksforgeeks.org/doublestream-average-java-examples/)

***Java 8 中的 Java . util . stream . double stream***处理原语的双打。它有助于以一种新的方式解决在数组中寻找最大值、在数组中寻找最小值、在数组中所有元素的和以及在数组中所有值的平均值等老问题。 **DoubleStream average()** 返回描述该流元素算术平均值的 OptionalDouble，如果该流为空，则返回空的可选值。如果任何记录的值是 NaN 或者总和在任何点都是 NaN，那么平均值就是 NaN。
**语法:**

```
OptionalDouble average()

Where, OptionalDouble is a container object 
which may or may not contain a double value.

```

**注意:**返回的平均值可能会因记录值的顺序而异。按绝对值递增排序的元素往往会产生更准确的结果。

**例 1 :**

```
// Java code for DoubleStream average()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        DoubleStream stream = DoubleStream.of(2.5, 3.6, 4.7, 5.0, 6.2);

        // OptionalDouble is a container object
        // which may or may not contain a
        // double value.
        OptionalDouble obj = stream.average();

        // If a value is present, isPresent() will
        // return true and getAsDouble() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

**Output:**

```
4.4

```