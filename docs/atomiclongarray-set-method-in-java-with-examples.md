# Java 中的 AtomicLongArray set()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-set-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . set()**是 Java 中的一个内置方法，它在 atomicongarray 的任何位置设置一个给定值。此方法将 AtomicLongArray 的索引值作为参数，并更新该索引处的值。此方法不返回值。函数 **set()** 类似于 **getAndSet()** 函数，但是前者不返回任何值，而后者在给定索引处返回值，然后在该索引处设置新值。

**语法:**

> 公共最终无效集(int i，long newValue)

**参数:**函数取两个参数:

*   *I*–要进行更新的索引值。*   *newValue* – The new value to update at the index.

    **返回值:**函数不返回值。

    下面的程序说明了上述方法:

    **程序 1:**

    ```java
    // Java program that demonstrates
    // the set() function

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
            int idx = 0;

            // The new value to update at idx
            long val = 10;

            // Updating the value at
            // idx applying set
            arr.set(idx, val);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```java
    The array : [1, 2, 3, 4, 5]
    The array after update : [10, 2, 3, 4, 5]

    ```

    **程序 2:**

    ```java
    // Java program that demonstrates
    // the set() function

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

            // The new value to update at idx
            long val = 100;

            // Updating the value at
            // idx applying set
            arr.set(idx, val);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```java
    The array : [1, 2, 3, 4, 5]
    The array after update : [1, 2, 3, 100, 5]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # set-int-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#set-int-long-)