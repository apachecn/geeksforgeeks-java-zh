# Java 中的 ConcurrentSkipListSet 天花板()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-天花板-java 中的方法/](https://www.geeksforgeeks.org/concurrentskiplistset-ceiling-method-in-java/)

**java . util . concurrentSkiplistset .天花板()**方法是 Java 中的内置函数，它返回该集合中大于或等于给定元素的最少元素，如果没有这样的元素，则返回 null。

**语法:**

```java
 ConcurrentSkipListSet.ceiling(E e)

```

**参数:**该函数接受单个参数 *e* ，即要匹配的元素。

**返回值:**该函数返回大于或等于 *e* 的最小元素，如果没有该元素，则返回空值。

**异常:**功能显示以下异常:

*   class castexception–如果指定的元素无法与集合中的当前元素进行比较*   NullPointerException – if the specified element is null

    下面的程序说明了 ConcurrentSkipListSet .天花板()方法:

    **程序 1:** 求一个数的上限。

    ```java
    // Java Program Demonstrate ceiling()
    // method of ConcurrentSkipListSet 

    import java.util.concurrent.*;

    class ConcurrentSkipListSetCeilingExample1 {
        public static void main(String[] args)
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer> Lset = 
                            new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            Lset.add(45);
            Lset.add(72);
            Lset.add(31);
            Lset.add(13);
            Lset.add(89);

            // Printing elements of the set
            System.out.println("The set contains: ");
            for (Integer i : Lset)
                System.out.print(i + " ");

            // Ceiling of 35
            System.out.println("\nCeiling of 35: " + Lset.ceiling(35));

            // Ceiling of 100
            System.out.println("\nCeiling of 100: " + Lset.ceiling(100));
        }
    }
    ```

    **Output:**

    ```java
    The set contains: 
    13 31 45 72 89 
    Ceiling of 35: 45

    Ceiling of 100: null

    ```

    **程序 2:** 显示天花板()中的空指针异常。

    ```java
    // Java Program Demonstrate ceiling()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;
    import java.io.*;

    class ConcurrentSkipListSetCeilingExample2 {
        public static void main(String[] args) throws IOException
        {
            // Creating a set object
            ConcurrentSkipListSet<Integer> Lset = 
                                new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            Lset.add(45);
            Lset.add(72);
            Lset.add(31);
            Lset.add(13);
            Lset.add(89);

            try {
                // Ceiling of null
                System.out.println("Ceiling of null: " + Lset.ceiling(null));
            }

            catch (Exception e) {
                System.out.println("Exception : " + e);
            }
        }
    }
    ```

    **Output:**

    ```java
    Exception : java.lang.NullPointerException

    ```

    **参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrentskiplistset . html #天花板(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#ceiling(E))