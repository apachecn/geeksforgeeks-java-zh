# Java 中的 AtomicLongArray getAndSet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-getandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . getandset()**是 Java 中的一个内置方法，它在 atomicongarray 的任何给定位置自动设置给定值。该方法将原子克隆数组的索引值和要设置的值作为参数。它返回给定索引处的值，然后在该索引处设置新值。函数 **getAndSet()** 类似于 **set()** 函数，但前者返回值，而后者不返回值。
**语法:**

> 公共最终长 getAndSet(int i，long newValue)

**参数:**该函数接受两个参数:

*   *I*–要进行更新的索引。*   *newValue* – The value to set at index *i*

    **返回值:**该函数返回更新前给定索引处的值，该值在*长*中。

    下面的程序说明了上述方法:

    **程序 1:**

    ```
    // Java program that demonstrates
    // the getAndSet() function

    import java.util.concurrent.atomic.AtomicLongArray;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 11, 12, 13, 14, 15 };

            // Initializing an AtomicLongArray with array a
            AtomicLongArray arr = new AtomicLongArray(a);

            // Displaying the AtomicLongArray
            System.out.println("The array : " + arr);

            // Index where operation is performed
            int idx = 0;

            // New value to set at idx
            long val = 100;

            // Updating the value at
            // idx applying getAndSet
            // and store previous value
            long prev = arr.getAndSet(idx, val);

            // Previous value at idx before update
            System.out.println("Value at index " + idx
                               + " before the update is "
                               + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [11, 12, 13, 14, 15]
    Value at index 0 before the update is 11
    The array after update : [100, 12, 13, 14, 15]

    ```

    **程序 2:**

    ```
    // Java program that demonstrates
    // the getAndSet() function

    import java.util.concurrent.atomic.AtomicLongArray;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 11, 12, 13, 14, 15 };

            // Initializing an AtomicLongArray with array a
            AtomicLongArray arr = new AtomicLongArray(a);

            // Displaying the AtomicLongArray
            System.out.println("The array : " + arr);

            // Index where operation is performed
            int idx = 3;

            // New value to set at idx
            long val = 10;

            // Updating the value at
            // idx applying getAndSet
            // and store previous value
            long prev = arr.getAndSet(idx, val);

            // Previous value at idx before update
            System.out.println("Value at index " + idx
                               + " before the update is "
                               + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [11, 12, 13, 14, 15]
    Value at index 3 before the update is 14
    The array after update : [11, 12, 13, 10, 15]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # getAndSet-int-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndSet-int-long-)