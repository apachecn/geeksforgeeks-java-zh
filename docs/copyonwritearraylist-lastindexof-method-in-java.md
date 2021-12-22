# Java 中的 copy onwriterarraylist last indexof()方法

> 原文:[https://www . geesforgeks . org/copy onwriterarraylist-last indexof-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-lastindexof-method-in-java/)

*   The **lastIndexOf(Object o)** method of **[CopyOnWriteArrayList](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** returns the last occurrence of the element passed in the list. It returns -1 if the element is not present in the list.

    **语法:**

    ```
    public int lastIndexOf(Object o)
    ```

    **参数:**该函数接受一个参数 *o* ，该参数的最后一次出现将被返回。

    **返回值:**函数返回元素的最后一次出现。如果该元素不在列表中，则返回-1。

    以下程序说明了上述功能:

    **程序 1:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // lastIndexOf() method in Java
    import java.util.concurrent.CopyOnWriteArrayList;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // create object of CopyOnWriteArrayList
            CopyOnWriteArrayList<Integer> ArrLis
                = new CopyOnWriteArrayList<Integer>();

            // Add elements
            ArrLis.add(32);
            ArrLis.add(67);
            ArrLis.add(67);
            ArrLis.add(100);

            // print CopyOnWriteArrayList
            System.out.println("CopyOnWriteArrayList: "
                                               + ArrLis);

            // last occurrence of 67
            System.out.println("lastIndexOf value: " 
                             + ArrLis.lastIndexOf(67));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 100]
    lastIndexOf value: 2

    ```

    **程序 2:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // lastIndexOf() method in Java
    import java.util.concurrent.CopyOnWriteArrayList;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // create object of CopyOnWriteArrayList
            CopyOnWriteArrayList<Integer> ArrLis
                = new CopyOnWriteArrayList<Integer>();

            // Add elements
            ArrLis.add(32);
            ArrLis.add(67);
            ArrLis.add(67);
            ArrLis.add(100);

            // print CopyOnWriteArrayList
            System.out.println("CopyOnWriteArrayList: " 
                                              + ArrLis);

            // 200 is not present
            System.out.println("lastIndexOf value: " 
                              + ArrLis.lastIndexOf(200));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 100]
    lastIndexOf value: -1

    ```

*   The **lastIndexOf(E e, int index)** method of **[CopyOnWriteArrayList](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** returns the last occurrence of the element passed in the list after position index. It returns -1 if the element is not present in the list.

    **语法:**

    ```
    public int lastIndexOf(E e, int index)
    ```

    **参数:**该函数接受两个参数，如下所述:

    *   **索引:**指定从中搜索事件的索引。
    *   **e** :指定最后一次从位置*索引*出现的元素将被返回。

    **返回值:**函数返回位置索引后元素的最后一次出现。如果该元素不在列表中，则返回-1。

    **异常:**如果指定的指数为负，该函数将抛出**指数。**

    以下程序说明了上述功能:

    **程序 1:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // lastIndexOf() method in Java
    import java.util.concurrent.CopyOnWriteArrayList;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // create object of CopyOnWriteArrayList
            CopyOnWriteArrayList<Integer> ArrLis
                = new CopyOnWriteArrayList<Integer>();

            // Add elements
            ArrLis.add(32);
            ArrLis.add(67);
            ArrLis.add(67);
            ArrLis.add(67);

            // print CopyOnWriteArrayList
            System.out.println("CopyOnWriteArrayList: " 
                                                 + ArrLis);

            // last occurrence of 67 from 2nd index
            System.out.println("lastIndexOf value: " 
                              + ArrLis.lastIndexOf(67, 2));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 67]
    lastIndexOf value: 2

    ```

    **程序 2:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // lastIndexOf() method in Java
    import java.util.concurrent.CopyOnWriteArrayList;
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {

            // create object of CopyOnWriteArrayList
            CopyOnWriteArrayList<Integer> ArrLis
                = new CopyOnWriteArrayList<Integer>();

            // Add elements
            ArrLis.add(32);
            ArrLis.add(67);
            ArrLis.add(67);
            ArrLis.add(100);

            // print CopyOnWriteArrayList
            System.out.println("CopyOnWriteArrayList: " 
                                              + ArrLis);

            // -1 is out of range, hence exception
            System.out.println("lastIndexOf value: " 
                           + ArrLis.lastIndexOf(-1, 200));
        }
    }
    ```

    **输出:**

    > 线程“main”Java . lang . arrayindexoutofboundsexception:-1
    > 在 Java . util . concurrent . copy onwriterarraylist . last indexof(copy onwriterarraylist . Java:198)
    > 在 Java . util . concurrent . copy onwriterarraylist . last indexof(copy onwriterarraylist . Java:263)
    > 在 GFG.main(GFG.java:24)

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copy onwriterarraylist . html # last indexof-E-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#lastIndexOf-E-int-)