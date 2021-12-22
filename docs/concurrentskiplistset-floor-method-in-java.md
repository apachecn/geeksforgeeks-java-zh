# Java 中的 ConcurrentSkipListSet floor()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-floor-in-method-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-floor-method-in-java/)

**java . util . concurrentSkiplistset**的 **floor()** 方法是 Java 中的一个内置函数，它返回该集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 null。

**语法:**

```
ConcurrentSkipListSet.floor(E e)
```

**参数:**该函数接受单个参数 *e* ，即要匹配的值。

**返回值:**该函数返回小于或等于 *e* 的最大元素，如果没有该元素，则返回空值。

**异常:**函数抛出以下异常:

*   **class castexception**–如果指定元素无法与集合中的当前元素进行比较。*   **NullPointerException** – if the specified element is null

    下面的程序说明了 ConcurrentSkipListSet.floor()方法:

    **程序 1:**

    ```
    // Java program to demonstrate floor()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;

    class ConcurrentSkipListSetFloorExample1 {
        public static void main(String[] args)
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer>
                Lset = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 10; i <= 50; i += 10)
                Lset.add(i);

            // Finding floor of 20 in the set
            System.out.println("The floor of 20 in the set "
                               + Lset.floor(20));

            // Finding floor of 39 in the set
            System.out.println("The floor of 39 in the set "
                               + Lset.floor(39));

            // Finding floor of 9 in the set
            System.out.println("The floor of 10 in the set "
                               + Lset.floor(9));
        }
    }
    ```

    **Output:**

    ```
    The floor of 20 in the set 20
    The floor of 39 in the set 30
    The floor of 10 in the set null

    ```

    **程序 2:** 在楼层()显示空指针异常的程序。

    ```
    // Java program to demonstrate floor()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;

    class ConcurrentSkipListSetFloorExample2 {
        public static void main(String[] args)
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer>
                Lset = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 10; i <= 50; i += 10)
                Lset.add(i);

            // Trying to find the floor of null
            try {
                System.out.println("The floor of null in the set "
                                   + Lset.floor(null));
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

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # floor-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#floor-E-)