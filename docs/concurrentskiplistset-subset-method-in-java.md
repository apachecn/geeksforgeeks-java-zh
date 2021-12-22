# Java 中的 ConcurrentSkipListSet subSet()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-subset-method-in-Java/](https://www.geeksforgeeks.org/concurrentskiplistset-subset-method-in-java/)

#### **子集(E fromElement，E toElement)**

**java . util . concurrentskiplistset**的**Subject()**方法是 Java 中的一个内置函数，它返回该集合中元素范围为从元素(包含)到元素(不包含)的部分的视图。(如果 fromElement 和 toElement 相等，则返回的集合为空。)返回的集合由该集合支持，因此返回集合中的变化反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。

**语法:**

```java
public NavigableSet subSet(E fromElement,
                     E toElement) 
```

**参数:**函数接受以下参数:

*   *从元素*–返回集合的低端点(含)。*   *toElement* – high endpoint (exclusive) of the returned set

    **返回值:**该函数返回一个导航集，该导航集是该集合的一部分的视图，该集合的元素范围从 fromElement(包含)到 toElement(不包含)。

    **异常:**函数抛出以下异常:

    *   *class castexception*–如果 fromElement 和 toElement 无法使用该集合的比较器进行相互比较(或者，如果该集合没有比较器，则使用自然排序)。如果 fromElement 或 toElement 无法与集合中当前的元素进行比较，则实现可能会引发此异常，但这不是必需的。*   *空指针异常*–如果 fromElement 或 toElement 为空*   *IllegalArgumentException* – if fromElement is greater than toElement; or if this set itself has a restricted range, and fromElement or toElement lies outside the bounds of the range.

    下面的程序说明了 ConcurrentSkipListSet.subSet()方法:

    **程序 1:**

    ```java
    // Java program to demonstrate subSet()
    // method of ConcurrentSkipListSet

    // Java Program Demonstrate subSet()
    // method of ConcurrentSkipListSet */
    import java.util.NavigableSet;
    import java.util.concurrent.ConcurrentSkipListSet;

    class ConcurrentSkipListSetSubSetExample1 {
        public static void main(String[] args)
        {

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 0; i <= 10; i++)
                set.add(i);

            // Printing the elements of the set
            System.out.println("Contents of the set: " + set);

            // Creating a subsetset object
            NavigableSet<Integer> sub_set = set.subSet(2, 8);

            // Printing the elements of the descending set
            System.out.println("Contents of the subset: " + sub_set);
        }
    }
    ```

    **Output:**

    ```java
    Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Contents of the subset: [2, 3, 4, 5, 6, 7]

    ```

    **程序 2:**

    ```java
    // Java program to demonstrate subSet()
    // method of ConcurrentSkipListSet

    // Java Program Demonstrate subSet()
    // method of ConcurrentSkipListSet */
    import java.util.NavigableSet;
    import java.util.concurrent.ConcurrentSkipListSet;

    class ConcurrentSkipListSetSubSetExample2 {
        public static void main(String[] args)
        {

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 0; i <= 10; i++)
                set.add(i);

            // Printing the elements of the set
            System.out.println("Contents of the set: " + set);

            try {
                // Creating a subsetset object
                NavigableSet<Integer> sub_set = set.subSet(2, null);
            }
            catch (Exception e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```java
    Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Exception: java.lang.NullPointerException

    ```

    #### **子集(E 从元素，布尔从包含，E 到元素，布尔到包含)**

    **java . util . concurrentskiplistset**的 **subSet()** 方法是 Java 中的一个内置函数，它返回该集合中元素范围为从一个元素到另一个元素的部分的视图。如果 fromElement 和 toElement 相等，则返回的集合为空，除非 fromInclusive 和 toInclusive 都为真。返回的集合由该集合支持，因此返回集合中的更改反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。返回的集合将在试图插入超出其范围的元素时抛出一个 IllegalArgumentException。

    **语法:**

    ```java
    public NavigableSet subSet(E fromElement,
                         boolean fromInclusive,
                         E toElement,
                         boolean toInclusive) 
    ```

    **参数:**函数接受以下参数:

    *   *从元素*–返回集合的低端点*   *从包含*–如果低端点将包含在返回的视图中，则为真*   *至元素*–返回集合的高端点*   *toInclusive* – true if the high endpoint is to be included in the returned view

    **返回值:**该函数返回该集合部分的视图，该集合的元素范围为从元素(包含)到元素(不包含)。

    **异常:**函数抛出以下异常:

    *   *class castexception*–如果 fromElement 和 toElement 无法使用该集合的比较器进行相互比较(或者，如果该集合没有比较器，则使用自然排序)。如果 fromElement 或 toElement 无法与集合中当前的元素进行比较，则实现可能会引发此异常，但这不是必需的。*   *空指针异常*–如果 fromElement 或 toElement 为空*   *IllegalArgumentException* – if fromElement is greater than toElement; or if this set itself has a restricted range, and fromElement or toElement lies outside the bounds of the range.

    下面的程序说明了 ConcurrentSkipListSet.subSet()方法:
    **程序 3:**

    ```java
    // Java Program Demonstrate subSet()
    // method of ConcurrentSkipListSet */
    import java.util.NavigableSet;
    import java.util.concurrent.ConcurrentSkipListSet;

    class ConcurrentSkipListSetSubSetExample3 {
        public static void main(String[] args)
        {

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 0; i <= 10; i++)
                set.add(i);

            // Printing the elements of the set
            System.out.println("Contents of the set: " + set);

            // Creating a subsetset object
            NavigableSet<Integer> sub_set = set.subSet(2, true, 8, true);

            // Printing the elements of the descending set
            System.out.println("Contents of the subset: " + sub_set);
        }
    }
    ```

    **Output:**

    ```java
    Contents of the set: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Contents of the subset: [2, 3, 4, 5, 6, 7, 8]

    ```

    **参考:**
    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # subSet-E-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-E-)

    [https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # subSet-E-boolean-E-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#subSet-E-boolean-E-boolean-)