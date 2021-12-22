# Java 中的 ConcurrentSkipListSet removeAll()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-removeall-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-removeall-method-in-java/)

**java . util . concurrentskiplistset**的 **removeAll()** 方法是 Java 中的一个内置函数，它从这个集合中返回并移除指定集合中包含的所有元素。如果指定的集合也是集合，则此操作会有效地修改该集合，使其值为两个集合的不对称集合差。

**语法:**

```java
public boolean removeAll(Collection c)
```

**参数:**该函数接受单个参数 *c*

**返回值:**如果该集合因调用而改变，则函数返回真。

**异常:**函数抛出以下异常:

*   **class castexception**–如果该集合中一个或多个元素的类型与指定集合不兼容*   **NullPointerException** – if the specified collection or any of its elements are null

    下面的程序说明了 concurrentskiplistset . removeall()方法:

    **程序 1:**

    ```java
    // Java program to demonstrate removeAll()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;
    import java.util.ArrayList;
    import java.util.List;

    class ConcurrentSkipListSetremoveAllExample1 {
        public static void main(String[] args)
        {

            // Initializing the List
            List<Integer> list = new ArrayList<Integer>();

            // Adding elements in the list
            for (int i = 1; i <= 10; i += 2)
                list.add(i);

            // Contents of the list
            System.out.println("Contents of the list: " + list);

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements in the set
            for (int i = 1; i <= 10; i++)
                set.add(i);

            // Contents of the set
            System.out.println("Contents of the set: " + set);

            // Remove all elements from the set which are in the list
            set.removeAll(list);

            // Contents of the set after removal
            System.out.println("Contents of the set after removal: "
                               + set);
        }
    }
    ```

    **Output:**

    ```java
    Contents of the list: [1, 3, 5, 7, 9]
    Contents of the set: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Contents of the set after removal: [2, 4, 6, 8, 10]

    ```

    **程序 2:** 在 removeAll()中显示 NullPOinterException 的程序。

    ```java
    // Java program to demonstrate removeAll()
    // method of ConcurrentSkipListSet

    import java.util.concurrent.*;
    import java.util.ArrayList;
    import java.util.List;

    class ConcurrentSkipListSetremoveAllExample1 {
        public static void main(String[] args)
        {

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements in the set
            for (int i = 1; i <= 10; i++)
                set.add(i);

            // Contents of the set
            System.out.println("Contents of the set: " + set);

            try {
                // Remove all elements from the set which are null
                set.removeAll(null);
            }
            catch (Exception e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```java
    Contents of the set: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Exception: java.lang.NullPointerException

    ```

    **参考:**

    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # removeAll-Java . util . collection-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#removeAll-java.util.Collection-)