# Java 中的 AtomicLongArray getAndAccumulate()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-getandaccumulate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandaccumulate-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . getandaccumulate()**是 Java 中的一个内置方法，它在将给定函数应用于当前值和给定值后，用结果自动更新 atomicongarray 的任何索引处的值，返回前一个值。此方法接受要执行操作的原子克隆数组的索引、执行操作的值和累加器函数作为参数。应用该函数时，索引处的当前值作为其第一个参数，给定的更新作为第二个参数。累加器函数应该没有副作用，因为当由于线程之间的争用导致尝试的更新失败时，它可以被重新应用。函数 **getAndAccumulate()** 与**accumulated gt()**类似，但前者在更新前返回值，后者在更新后返回值。

**语法:**

> 公共最终长 getAndAccumulate(int i，long x，LongBinaryOperator 累加器函数)

**参数:**该函数接受三个参数:

*   *I*–要进行更新的索引。*   *x*–用 I 处的值进行运算的值*   *accumulatorFunction* – A side-effect-free function of two arguments.

    **返回值:**该函数返回更新前的值，该值在*长*中。
    以下程序说明上述方法:
    **程序 1:**

    ```
    // Java program that demonstrates
    // the getAndAccumulate() function

    import java.util.concurrent.atomic.AtomicLongArray;
    import java.util.function.LongBinaryOperator;

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
            int idx = 4;

            // Value to make operation with value at idx
            long x = 5;

            // Declaring the accumulatorFunction
            LongBinaryOperator add = (u, v) -> u + v;

            // Updating the value at idx
            // applying getAndAccumulate
            long prev = arr.getAndAccumulate(idx, x, add);

            // The previous value at idx
            System.out.println("Value at index " + idx
                               + " before update is "
                               + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    Value at index 4 before update is 5
    The array after update : [1, 2, 3, 4, 10]

    ```

    **程序 2:**

    ```
    // Java program that demonstrates
    // the getAndAccumulate() function

    import java.util.concurrent.atomic.AtomicLongArray;
    import java.util.function.LongBinaryOperator;

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
            int idx = 0;

            // Value to make operation with value at idx
            long x = 6;

            // Declaring the accumulatorFunction
            LongBinaryOperator sub = (u, v) -> u - v;

            // Updating the value at idx
            // applying getAndAccumulate
            long prev = arr.getAndAccumulate(idx, x, sub);

            // The previous value at idx
            System.out.println("Value at index " + idx
                               + " before update is "
                               + prev);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    Value at index 0 before update is 1
    The array after update : [-5, 2, 3, 4, 5]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # getAndAccumulate-int-long-Java . util . function . longbinaryoperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndAccumulate-int-long-java.util.function.LongBinaryOperator-)