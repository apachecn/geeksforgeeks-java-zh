# Java 中的 LinkedList addAll()方法

> 原文:[https://www . geesforgeks . org/Java-util-linked list-addall-method-in-Java/](https://www.geeksforgeeks.org/java-util-linkedlist-addall-method-in-java/)

1.  **java.util.LinkedList.addAll(Collection C)**: This method is used to append all of the elements from the collection passed as parameter to this function to the end of a list keeping in mind the order of return by the collections iterator.

    **语法:**

    ```
    *boolean* addAll(Collection C)
    ```

    **参数:**参数 *C* 是数组列表的集合。它是需要在列表末尾追加元素的集合。

    **返回值:**如果至少执行了一个追加动作，则该方法返回真。

    下面的程序说明了 Java.util.LinkedList.addAll()方法:

    ```
    // Java code to illustrate boolean addAll()
    import java.util.*;
    import java.util.LinkedList;
    import java.util.ArrayList;

    public class LinkedListDemo {
       public static void main(String args[]) {

          // Creating an empty LinkedList
          LinkedList<String> list = new LinkedList<String>();

          // Use add() method to add elements in the list
          list.add("Geeks");
          list.add("for");
          list.add("Geeks");
          list.add("10");
          list.add("20");

          // A collection is created
          Collection<String> collect = new ArrayList<String>();
          collect.add("A");
          collect.add("Computer");
          collect.add("Portal");
          collect.add("for");
          collect.add("Geeks");

          // Displaying the list
          System.out.println("The LinkedList is: " + list);

          // Appending the collection to the list
          list.addAll(collect);

         // Clearing the list using clear() and displaying
         System.out.println("The new linked list is: " + list);

       }
    }
    ```

    **Output:**

    ```
    The LinkedList is: [Geeks, for, Geeks, 10, 20]
    The new linked list is: [Geeks, for, Geeks, 10, 20, A, Computer, Portal, for, Geeks]

    ```

2.  **java.util.LinkedList.addAll(int index, Collection C)**: This method is used to append all of the elements from the collection passed as parameter to this function at a specific index or position of a list.

    **语法:**

    ```
    boolean addAll(int index, Collection C)
    ```

    **参数:**该函数接受两个参数，如上语法所示，描述如下。

    *   **索引**:该参数为整数数据类型，指定列表中从容器元素插入位置开始的位置。
    *   **C** :是数组列表的集合。它是需要追加元素的集合。

    **返回值:**如果至少执行了一个追加操作，则该方法返回真。

    下面的程序说明了 Java.util.LinkedList.addAll()方法:

    ```
    // Java code to illustrate boolean addAll()
    import java.util.*;
    import java.util.LinkedList;
    import java.util.ArrayList;

    public class LinkedListDemo {
       public static void main(String args[]) {

          // Creating an empty LinkedList
          LinkedList<String> list = new LinkedList<String>();

          // Use add() method to add elements in the list
          list.add("Geeks");
          list.add("for");
          list.add("Geeks");
          list.add("10");
          list.add("20");

          // Creating a Collection
          Collection<String> collect = new ArrayList<String>();
          collect.add("A");
          collect.add("Computer");
          collect.add("Portal");
          collect.add("for");
          collect.add("Geeks");

          // Displaying the list
          System.out.println("The LinkedList is: " + list);

          // Appending the collection to the list
          list.addAll(1, collect);

         // Clearing the list using clear() and displaying
         System.out.println("The new linked list is: " + list);

       }
    }
    ```

    **Output:**

    ```
    The LinkedList is: [Geeks, for, Geeks, 10, 20]
    The new linked list is: [Geeks, A, Computer, Portal, for, Geeks, for, Geeks, 10, 20]

    ```