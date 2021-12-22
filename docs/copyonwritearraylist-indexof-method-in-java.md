# Java 中的 CopyOnWriteArrayList indexOf()方法

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-indexof-method-in-Java/](https://www.geeksforgeeks.org/copyonwritearraylist-indexof-method-in-java/)

*   The **indexOf(Object o)** method of **[CopyOnWriteArrayList](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** returns the first occurrence of the element passed in the list. It returns -1 if the element is not present in the list.

    **语法:**

    ```
    public int indexOf(Object o)
    ```

    **参数:**该函数接受一个参数 *o* ，该参数的第一次出现将被返回。

    **返回值:**函数返回元素的第一次出现。如果该元素不在列表中，则返回-1。

    以下程序说明了上述功能:

    **程序 1:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // indexOf() method in Java
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
            System.out.println("CopyOnWriteArrayList: " + ArrLis);

            // first occurrence of 67
            System.out.println("indexOf value: " + ArrLis.indexOf(67));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 100]
    indexOf value: 1

    ```

    **程序 2:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // indexOf() method in Java
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
            System.out.println("indexOf value: " 
                             + ArrLis.indexOf(200));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 100]
    indexOf value: -1

    ```

*   The **indexOf(E e, int index)** method of **[CopyOnWriteArrayList](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)** returns the first occurrence of the element passed in the list after position index. It returns -1 if the element is not present in the list.

    **语法:**

    ```
    public int indexOf(E e, int index)
    ```

    **参数:**该函数接受两个参数，如下所述:

    *   **索引:**指定从中搜索事件的索引。
    *   **e** :指定从位置*索引*第一次出现要返回的元素。

    **返回值:**函数返回位置索引后元素的第一次出现。如果该元素不在列表中，则返回-1。

    **异常:**如果指定的指数为负，该函数将抛出**指数。**

    以下程序说明了上述功能:

    **程序 1:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // indexOf() method in Java
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

            // first occurrence of 67 from 2nd index
            System.out.println("indexOf value: " 
                              + ArrLis.indexOf(67, 2));
        }
    }
    ```

    **Output:**

    ```
    CopyOnWriteArrayList: [32, 67, 67, 67]
    indexOf value: 2

    ```

    **程序 2:**

    ```
    // Java Program to illustrate the CopyOnWriteArrayList
    // indexOf() method in Java
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
            System.out.println("indexOf value: " 
                          + ArrLis.indexOf(-1, 200));
        }
    }
    ```

    **输出:**

    ```
    Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: -1
        at java.util.concurrent.CopyOnWriteArrayList.indexOf(CopyOnWriteArrayList.java:198)
        at java.util.concurrent.CopyOnWriteArrayList.indexOf(CopyOnWriteArrayList.java:263)
        at GFG.main(GFG.java:24)
    ```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/copyonwriterarylist . html # indexOf-E-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CopyOnWriteArrayList.html#indexOf-E-int-)