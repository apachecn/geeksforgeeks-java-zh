# Java 中的 AtomicLongArray accumulateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-accumulatedget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-accumulateandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicongarray . accumulate dget()**是 Java 中的一个内置方法，它通过将给定函数应用于当前值和给定值的结果自动更新索引 I 处的元素，返回更新后的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。该函数的第一个参数是索引 I 处的当前值，第二个参数是给定的更新。

**语法:**

> 公共最终长累计数(int i，long x，LongBinaryOperator 累计函数)

**参数:**该函数接受三个参数:

*   *I*–更新的索引是马达。*   *x*–用 *i* 的值进行运算的值*   *accumulatorFunction* – A side-effect-free function of two arguments.

    **返回值:**该函数返回更新后的值，该值在*长*内。

    以下程序说明了上述方法:
    **程序 1:**

    ```
    // Java program that demonstrates
    // the accumulateAndGet() function

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
            // applying accumulatorFunction
            arr.accumulateAndGet(idx, x, add);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [1, 2, 3, 4, 5]
    The array after update : [1, 2, 3, 4, 10]

    ```

    **程序 2:**

    ```
    // Java program that demonstrates
    // the accumulateAndGet() function

    import java.util.concurrent.atomic.AtomicLongArray;
    import java.util.function.LongBinaryOperator;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            long a[] = { 17, 22, 33, 44, 55 };

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
            // applying accumulatorFunction
            arr.accumulateAndGet(idx, x, sub);

            // Displaying the AtomicLongArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```
    The array : [17, 22, 33, 44, 55]
    The array after update : [11, 22, 33, 44, 55]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # accumulated gt-int-long-Java . util . function . longbinaryoperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#accumulateAndGet-int-long-java.util.function.LongBinaryOperator-)