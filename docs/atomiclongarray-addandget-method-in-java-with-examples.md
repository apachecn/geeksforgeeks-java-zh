# Java 中的 AtomicLongArray addAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-addandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-addandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . addandget()**是 Java 中的一个内置方法，它在 atomicongarray 的索引处自动将给定的值添加到元素中。此方法将索引值和要添加的值作为参数，并返回此索引处的更新值。

**语法:**

```
public long addAndGet(int i, long delta)

```

**参数:**该函数接受两个参数:

*   *I*–要添加值的索引。*   *delta* – The value to be added.

    **返回值:**该函数返回更新后的值，该值在*长*内。

    以下程序说明了上述方法:
    **程序 1:**

    ```
    // Java program that demonstrates
    // the addAndGet() function

    import java.util.concurrent.atomic.AtomicLongArray;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 10, 22, 33, 44, 55 };

            // Initializing an AtomicLongArray with array a
            AtomicLongArray arr = new AtomicLongArray(a);

            // Displaying the AtomicLongArray
            System.out.println("The array : " + arr);

            // Index where value is to be added
            int idx = 0;

            // Value to add with value at idx
            long x = 16;

            // Updating the value at
            // idx applying addAndGet
            arr.addAndGet(idx, x);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [10, 22, 33, 44, 55]
    The array after update : [26, 22, 33, 44, 55]

    ```

    **程序 2:**

    ```
    // Java program that demonstrates
    // the addAndGet() function

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

            // Index where value is to be added
            int idx = 3;

            // Value to add with value at idx
            long x = 16;

            // Updating the value at
            // idx applying addAndGet
            arr.addAndGet(idx, x);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    The array after update : [1, 2, 3, 20, 5]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # addAndGet-int-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#addAndGet-int-long-)