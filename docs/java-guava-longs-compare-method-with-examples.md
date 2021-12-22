# 爪哇番石榴| Longs.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-compare-method-with-examples/)

**Longs.compare()** 法番石榴的 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)用于比较两个指定的 *long* 值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```
public static int compare(long a, long b)

```

**参数:**该方法接受两个参数:

*   **a:** 第一个比较的长物体。
*   **b:** 这是第二个要比较的长对象。

**返回类型:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   正值“a”大于“b”，
*   负值“a”小于“b”

**异常:**该方法没有任何异常。

**例 1:**

```
// Java code to show implementation of
// Guava's Longs.compare() method
import com.google.common.primitives.Longs;

class GFG {
    public static void main(String[] args)
    {
        long a = 5L;
        long b = 5L;

        // compare method in Long class
        int output = Longs.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 5 and 5 : 0

```

**例 2:**

```
// Java code to show implementation of
// Guava's Longs.compare() method
import com.google.common.primitives.Longs;

class GFG {
    public static void main(String[] args)
    {
        long a = 5L;
        long b = 4L;

        // compare method in Long class
        int output = Longs.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 5 and 4 : 1

```

**例 3:**

```
// Java code to show implementation of
// Guava's Longs.compare() method
import com.google.common.primitives.Longs;

class GFG {
    public static void main(String[] args)
    {
        long a = 4L;
        long b = 5L;

        // compare method in Long class
        int output = Longs.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4 and 5 : -1

```