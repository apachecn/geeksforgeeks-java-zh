# Java 中的 AtomicIntegerArray accumulate dget()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-accumulated get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-accumulateandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomictegerarray . accumulatedget()**是 Java 中的一个内置方法，它会用给定函数应用于当前值和给定值的结果自动更新索引 I 处的元素，并返回更新后的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。该函数的第一个参数是索引 I 处的当前值，第二个参数是给定的更新。

**语法:**

> 公共最终整数累计数(整数 I，整数 x，整数运算符累计函数)

**参数:**该函数接受三个参数:

*   *I*–更新的索引是马达。*   *x*–用 *i* 的值进行运算的值*   *accumulatorFunction* – A side-effect-free function of two arguments.

    **返回值:**该函数返回更新后的值，该值在*整数*中。

    以下程序说明了上述方法:
    **程序 1:**

    ```java
    // Java program that demonstrates
    // the accumulateAndGet() function

    import java.util.concurrent.atomic.AtomicIntegerArray;
    import java.util.function.IntBinaryOperator;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            int a[] = { 1, 2, 3, 4, 5 };

            // Initializing an AtomicIntegerArray with array a
            AtomicIntegerArray arr = new AtomicIntegerArray(a);

            // Displaying the AtomicIntegerArray
            System.out.println("The array : " + arr);

            // Index where update is to be made
            int idx = 4;

            // Value to make operation with value at idx
            int x = 5;

            // Declaring the accumulatorFunction
            IntBinaryOperator add = (u, v) -> u + v;

            // Updating the value at idx
            // applying accumulatorFunction
            arr.accumulateAndGet(idx, x, add);

            // Displaying the AtomicIntegerArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```java
    The array : [1, 2, 3, 4, 5]
    The array after update : [1, 2, 3, 4, 10]

    ```

    **程序 2:**

    ```java
    // Java program that demonstrates
    // the accumulateAndGet() function

    import java.util.concurrent.atomic.AtomicIntegerArray;
    import java.util.function.IntBinaryOperator;

    public class GFG {
        public static void main(String args[])
        {
            // Initializing an array
            int a[] = { 17, 22, 33, 44, 55 };

            // Initializing an AtomicIntegerArray with array a
            AtomicIntegerArray arr = new AtomicIntegerArray(a);

            // Displaying the AtomicIntegerArray
            System.out.println("The array : " + arr);

            // Index where update is to be made
            int idx = 0;

            // Value to make operation with value at idx
            int x = 6;

            // Declaring the accumulatorFunction
            IntBinaryOperator sub = (u, v) -> u - v;

            // Updating the value at idx
            // applying accumulatorFunction
            arr.accumulateAndGet(idx, x, sub);

            // Displaying the AtomicIntegerArray
            System.out.println("The array after update : "
                               + arr);
        }
    }
    ```

    **Output:**

    ```java
    The array : [17, 22, 33, 44, 55]
    The array after update : [11, 22, 33, 44, 55]

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicntegerarray . html # getAndAccumulate-int-int-Java . util . function . int binaryoperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndAccumulate-int-int-java.util.function.IntBinaryOperator-)