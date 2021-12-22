# Java 中的 AtomicLongArray getAndDecrement()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-getandreduction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getanddecrement-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicongarray . GetAndDefault()**是 Java 中的一个内置方法，它会将给定索引处的值自动递减 1。此方法获取 AtomicLongArray 的索引值，并返回该索引处的值，然后递减该索引处的值。函数**getanddecadel()**与**decadend get()**类似，但后者返回减量后的值，而前者返回减量前的值。

**语法:**

> 公共最终长 GetAndDefault(int I)

**参数:**该函数接受单个参数 *i* ，该参数是执行减 1 操作的索引。

**返回值:**该函数返回在减量操作之前在位于*长*的索引处的值。

以下程序说明了上述方法:
**程序 1:**

```java
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Decrementing the value at
        // idx applying getAndDecrement
        // and storing previous value
        long prev = arr.getAndDecrement(idx);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before decrement is "
                           + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after decrement : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
Value at index 3 before decrement is 4
The array after decrement : [1, 2, 3, 3, 5]

```

**程序 2:**

```java
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 10, 20, 30, 40, 50 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Decrementing the value at
        // idx applying getAndDecrement
        // and storing previous value
        long prev = arr.getAndDecrement(idx);

        // The previous value at idx
        System.out.println("Value at index " + idx
                           + " before decrement is "
                           + prev);

        // Displaying the AtomicLongArray
        System.out.println("The array after decrement : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [10, 20, 30, 40, 50]
Value at index 0 before decrement is 10
The array after decrement : [9, 20, 30, 40, 50]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # getanddecade-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndDecrement-int-)