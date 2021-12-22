# Java 中的 ConcurrentSkipListSet higher()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-higher-in-method-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-higher-method-in-java/)

**java . util . concurrentskiplistset**的 **higher(E e)** 方法是 Java 中的一个内置函数，它返回这个集合中严格大于给定元素的最少元素，如果没有这样的元素，则返回 null。

**语法:**

```
public E higher(E e)
```

**参数:**该函数接受单个参数 *e* ，即要匹配的值

**返回值:**函数返回大于 e 的最小元素，如果没有这样的元素，则返回 null。

**异常:**函数抛出以下异常:

*   **class castexception**–如果指定元素无法与集合中的当前元素进行比较。*   **NullPointerException** – if the specified element is null

    下面的程序说明了 concurrentskiplistset . higher(E E)方法:

    **程序 1:**

    ```
    // Java program to demonstrate higher()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;

    class ConcurrentSkipListSetHigherExample1 {
        public static void main(String[] args)
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer>
                Lset = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 10; i <= 50; i += 10)
                Lset.add(i);

            // Finding higher of 20 in the set
            System.out.println("The higher of 20 in the set: "
                               + Lset.higher(20));

            // Finding higher of 39 in the set
            System.out.println("The higher of 39 in the set: "
                               + Lset.higher(39));

            // Finding higher of 50 in the set
            System.out.println("The higher of 50 in the set: "
                               + Lset.higher(50));
        }
    }
    ```

    **Output:**

    ```
    The higher of 20 in the set: 30
    The higher of 39 in the set: 40
    The higher of 50 in the set: null

    ```

    **程序 2:** 以更高的()显示空指针异常的程序。

    ```
    // Java program to demonstrate higher()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;

    class ConcurrentSkipListSetHigherExample1 {
        public static void main(String[] args)
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer>
                Lset = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 10; i <= 50; i += 10)
                Lset.add(i);

            try {
                // Trying to find higher of "null" in the set
                System.out.println("The higher of null in the set: "
                                   + Lset.higher(null));
            }
            catch (Exception e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```
    Exception: java.lang.NullPointerException

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # higher-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#higher-E-)