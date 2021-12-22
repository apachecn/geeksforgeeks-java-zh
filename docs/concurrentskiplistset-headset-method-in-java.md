# Java 中的 ConcurrentSkipListSet headSet()方法

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-头戴式耳机-java 中的方法/](https://www.geeksforgeeks.org/concurrentskiplistset-headset-method-in-java/)

#### **耳机(和托儿)**

**java . util . concurrentskiplistset . headset()**方法是 Java 中的内置函数，它返回该集合中元素严格小于 toElement 的部分的视图。返回的集合由该集合支持，因此返回集合中的更改反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。

**语法:**

```java
public NavigableSet headSet(E toElement)
```

**参数:**该函数接受单个参数*到元素*，即返回集合的高端点。

**返回值:**该函数返回一个**导航集**，它是该集合中元素严格小于 to 元素的部分的视图。

以下程序说明了 concurrentskiplistset . headset(E to element)方法:
**程序 1:**

```java
// Java Program Demonstrate headSet()
// method of ConcurrentSkipListSet */
import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetHeadSetExample1 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            set.add(i);

        // Creating a headSet object with upper limit 30
        NavigableSet<Integer> hd_set = set.headSet(30);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        // Printing the elements of the headSet set
        System.out.println("Contents of the headset"
                           + " with upper limit 30: "
                           + hd_set);
    }
}
```

**Output:**

```java
Contents of the set: [10, 20, 30, 40, 50]
Contents of the headset with upper limit 30: [10, 20]

```

**程序 2:** 显示空指针异常的程序。

```java
// Java Program Demonstrate headSet()
// method of ConcurrentSkipListSet */
import java.util.NavigableSet;
import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetHeadSetExample2 {
    public static void main(String[] args)
    {

        // Initializing the set
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        for (int i = 10; i <= 50; i += 10)
            set.add(i);

        // Printing the elements of the set
        System.out.println("Contents of the set: " + set);

        try {
            // Trying to creating a headSet object with upper limit null
            NavigableSet<Integer> hd_set = set.headSet(null);
        }

        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
        // Printing the elements of the headSet set
        // System.out.println("Contents of the headset"
+" with upper limit 30: "+ hd_set);
    }
}
```

**Output:**

```java
Contents of the set: [10, 20, 30, 40, 50]
Exception: java.lang.NullPointerException

```

#### **头戴式耳机(E toElement，含布尔型)**

**java . util . concurrentskiplistset . headset()**方法是 Java 中的内置函数，它返回该集合中元素小于(或等于，如果包含为真)toElement 的部分的视图。返回的集合由该集合支持，因此返回集合中的更改反映在该集合中，反之亦然。返回的集合支持该集合支持的所有可选集合操作。

**语法:**

```java
public NavigableSet headSet(E toElement,
                      boolean inclusive) 
```

**参数:**函数接受以下参数

*   *至元素*，即返回集合的高端点。*   *inclusive* – true if the high endpoint is to be included in the returned view.

    **返回值:**该函数返回一个导航集，该导航集是该集合中元素小于(或等于，如果包含为真)元素的部分的视图。

    下面的程序说明了 concurrentskiplistset . headset(E to element，布尔包含)方法:

    **程序 3:**

    ```java
    // Java Program Demonstrate headSet()
    // method of ConcurrentSkipListSet */

    import java.util.NavigableSet;
    import java.util.concurrent.ConcurrentSkipListSet;

    class ConcurrentSkipListSetHeadSetExample3 {
        public static void main(String[] args)
        {

            // Initializing the set
            ConcurrentSkipListSet<Integer>
                set = new ConcurrentSkipListSet<Integer>();

            // Adding elements to this set
            for (int i = 10; i <= 50; i += 10)
                set.add(i);

            // Creating a headSet object with upper limit 30 inclusive
            NavigableSet<Integer> hd_set = set.headSet(30, true);

            // Printing the elements of the set
            System.out.println("Contents of the set: " + set);

            // Printing the elements of the headSet set
            System.out.println("Contents of the headset"
                               + " with upper limit 30 inclusive: "
                               + hd_set);
        }
    }
    ```

    **Output:**

    ```java
    Contents of the set: [10, 20, 30, 40, 50]
    Contents of the headset with upper limit 30 inclusive: [10, 20, 30]

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrentskiplistset . html # headSet-E-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentSkipListSet.html#headSet-E-)