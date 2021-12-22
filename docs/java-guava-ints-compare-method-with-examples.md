# 爪哇番石榴| Ints.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-ints-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-ints-compare-method-with-examples/)

**Ints.compare()** 是番石榴库中 [Ints 类](https://www.geeksforgeeks.org/ints-class-guava-java/)的一种方法，用于比较两个给定的 *int* 值。它将两个整数作为要比较的参数。它根据指定整数的比较结果返回一个比较器值。
**语法:**

```java
public static int compare(int a, int b)
```

**参数:**该方法取两个参数:

*   **a:** 是第一个要比较的**整数**值。
*   **b:** 这是要比较的第二个**整数**值。

**返回值:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   正值“a”大于“b”，
*   负值“a”小于“b”

下面的程序说明了上述方法的使用:
**例-1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// Guava's Ints.compare() method
import com.google.common.primitives.Ints;
import java.util.List;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Ints.compare() method to
        // compare the two specified int
        // values in the standard way
        // This should return positive number
        // as a is greater than b
        System.out.println(Ints.compare(5, 3));
    }
}
```

**Output:** 

```java
1
```

**示例-2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to show implementation of
// Guava's Ints.compare() method
import com.google.common.primitives.Ints;
import java.util.List;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Using Ints.compare() method to
        // compare the two specified int
        // values in the standard way
        // This should return 0 as a == b
        System.out.println(Ints.compare(2, 2));
    }
}
```

**Output:** 

```java
0
```