# Java 中的 AtomicReferenceArray updateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-updateandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-updateandget-method-in-java-with-examples/)

**原子引用数组**类的 **updateAndGet()** 方法用于原子更新，通过对当前值应用指定的更新函数操作来更新原子引用数组的当前值。它将 updateFunction 接口的一个对象作为参数，并将该对象中指定的操作应用于当前值。它返回前一个值。
**语法:**

```java
public final V updateAndGet(
  UnaryOperator<V> updateFunction)
```

**参数:**此方法接受:

*   索引 **i** 更新索引值
*   **updateFunction** 这是一个无副作用的功能。

**返回值:**此方法返回前一个值。
以下程序说明了 updateAndGet()方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReferenceArray.updateAndGet() method

import java.util.concurrent.atomic.*;
import java.util.function.UnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // an array
        String a[]
            = { "GFG", "JS", "PYTHON", "JAVA" };

        // AtomicReferenceArray with array
        AtomicReferenceArray<String> array
            = new AtomicReferenceArray<>(a);

        // Print AtomicReferenceArray
        System.out.println(
            "The AtomicReferenceArray before update : "
            + array);

        // Index
        int index = 2;

        // Declaring the accumulatorFunction
        // applying function
        UnaryOperator add
            = (u) -> u.toString() + " and ML";

        // apply updateAndGet()
        String value
            = array.updateAndGet(index, add);

        // print AtomicReferenceArray
        System.out.println("updated value of index 2:"
                           + value);
        System.out.println(
            "The AtomicReferenceArray after update: "
            + array);
    }
}
```

**Output:**