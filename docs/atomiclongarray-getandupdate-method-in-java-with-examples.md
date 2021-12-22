# Java 中的 AtomicLongArray getAndUpdate()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-getandupdate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandupdate-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . Getandupdate()**是 Java 中的一个内置方法，它在对 atomicongarray 的任何给定索引处的值应用给定的更新函数后，更新该索引处的值。该方法将原子克隆数组的索引值和更新函数作为参数，并通过对该值应用更新函数来更新该索引处的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。 **getAndUpdate()** 和 **updateAndGet()** 函数唯一的区别是前者返回更新前的值，后者返回更新后的值。

**语法:**

> 公共最终长 getAndUpdate(int i，longunaryooperator updateFunction)

 **参数:**该函数接受两个参数:

*   *i* 是要进行更新的索引。*   *updateFunction* which is the update function of single argument that tells what update is to be made.

    **返回值:**函数返回一个长值，即应用指定的更新函数后的值。

    以下程序说明了上述方法:
    **程序 1:**

    ```
    // Java program that demonstrates
    // the getAndUpdate() function

    import java.util.concurrent.atomic.AtomicLongArray;
    import java.util.function.LongUnaryOperator;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 1, 2, 3, 4, 5 };

            // Initializing an AtomicLongArray with array a
            AtomicLongArray arr = new AtomicLongArray(a);

            // Displaying the AtomicLongArray
            System.out.println("The array : " + arr);

            // Index where update is to be made
            int idx = 3;

            // Declaring the updateFunction
            LongUnaryOperator squaredFunction = (l) -> l * l;

            // Updating the value at idx
            // applying updateFunction and
            // storing the previous value
            long prev = arr.getAndUpdate(idx, squaredFunction);

            // Displaying the previous value
            System.out.println("The value before update"
                               + " at index " + idx
                               + " is " + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    The value before update at index 3 is 4
    The array after update : [1, 2, 3, 16, 5]

    ```

    **程序 2:**

    ```
    // Java program that demonstrates
    // the getAndUpdate() function

    import java.util.concurrent.atomic.AtomicLongArray;
    import java.util.function.LongUnaryOperator;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 1, 2, 3, 4, 5 };

            // Initializing an AtomicLongArray with array a
            AtomicLongArray arr = new AtomicLongArray(a);

            // Displaying the AtomicLongArray
            System.out.println("The array : " + arr);

            // Index where update is to be made
            int idx = 3;

            // Declaring the updateFunction
            LongUnaryOperator cubeFunction = (l) -> l * l * l;

            // Updating the value at idx
            // applying updateFunction and
            // storing the previous value
            long prev = arr.getAndUpdate(idx, cubeFunction);

            // Displaying the previous value
            System.out.println("The value before update"
                               + " at index " + idx
                               + " is " + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    The value before update at index 3 is 4
    The array after update : [1, 2, 3, 64, 5]

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # getAndUpdate-int-Java . util . function . longunaryooperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndUpdate-int-java.util.function.LongUnaryOperator-)