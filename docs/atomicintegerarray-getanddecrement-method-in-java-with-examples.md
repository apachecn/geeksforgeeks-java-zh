# Java 中的 AtomicIntegerArray getAndDecrement()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-getandreduction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-getanddecrement-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicntegerarray . GetAndDefault()**是 Java 中的一个内置方法，它会自动将给定索引处的值递减 1。该方法获取 AtomicIntegerArray 的索引值，并返回该索引处的值，然后递减该索引处的值。函数**getanddecadel()**与**decadend get()**类似，但后者返回减量后的值，而前者返回减量前的值。

**语法:**

```
public final int getAndDecrement(int i)

```

**参数:**该函数接受单个参数 *i* ，该参数是执行减 1 操作的索引。

**返回值:**该函数返回减量操作前在 *int* 中的索引处的值。

以下程序说明了上述方法:
**程序 1:**

```
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Decrementing the value at
        // idx applying getAndDecrement
        // and storing previous value
        int prev = arr.getAndDecrement(idx);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before decrement is "
                           + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after decrement : "
                           + arr);
    }
}
```

**Output:**

```
The array : [1, 2, 3, 4, 5]
Value at index 3 before decrement is 4
The array after decrement : [1, 2, 3, 3, 5]

```

**程序 2:**

```
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 10, 20, 30, 40, 50 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Decrementing the value at
        // idx applying getAndDecrement
        // and storing previous value
        int prev = arr.getAndDecrement(idx);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before decrement is "
                           + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after decrement : "
                           + arr);
    }
}
```

**Output:**

```
The array : [10, 20, 30, 40, 50]
Value at index 0 before decrement is 10
The array after decrement : [9, 20, 30, 40, 50]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomic/atomicintegerarray . html # getandreduction(int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndDecrement(int))