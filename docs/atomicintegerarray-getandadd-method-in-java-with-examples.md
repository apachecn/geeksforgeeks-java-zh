# Java 中的 AtomicIntegerArray getAndAdd()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintgerarray-getandad-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-getandadd-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . GetAnDadd()**是 Java 中的一个内置方法，它在 atomicntegerarray 的索引处自动给元素添加给定值。此方法将原子数组的索引值和要添加的值作为参数，并在添加操作之前返回该值。函数 **getAndAdd()** 与 **addAndGet()** 类似，但前者函数返回加法运算前的值，后者返回加法运算后的值。
**语法:**

```java
public final int getAndAdd(int i, int delta)
```

**参数:**该函数接受两个参数:

*   *I*–要添加值的索引。
*   *δ*–要添加的值。

**返回值:**该函数返回加法运算前的值，该值在*整数*中。
以下程序举例说明上述方法:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 10, 22, 33, 44, 55 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where value is to be added
        int idx = 0;

        // Value to add with value at idx
        int x = 16;

        // Updating the value at
        // idx applying getAndAdd and
        // storing the previous value
        int prev = arr.getAndAdd(idx, x);

        // Previous value at index idx
        // before update
        System.out.println("Value at index " + idx
                           + " before update is " + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:** 

```java
The array : [10, 22, 33, 44, 55]
Value at index 0 before update is 10
The array after update : [26, 22, 33, 44, 55]
```