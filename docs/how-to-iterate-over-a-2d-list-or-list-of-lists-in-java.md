# 如何在 Java 中迭代 2D 列表(列表列表)

> 原文:[https://www . geesforgeks . org/如何在 2d 列表或列表列表上迭代 java/](https://www.geeksforgeeks.org/how-to-iterate-over-a-2d-list-or-list-of-lists-in-java/)

给定一个 2D 列表，任务是在 Java 中迭代这个 2D 列表。

**2D 列表(list of list)**
2D 列表是指一个列表，即列表中的每一行都是另一个列表。

```
[
  [5, 10],
  [1], 
  [20, 30, 40]
] 

```

**迭代 2D 列表:**在 Java 中有两种迭代列表的方法。

1.  **Iterating over the list of lists using loop:**
    *   获取迭代的 2D 列表
    *   我们需要两个 [for-each 循环](https://www.geeksforgeeks.org/for-each-loop-in-java/)来成功迭代 2D 列表。
    *   在第一个 for-each 循环中，2D 列表的每一行都将作为一个单独的列表

        ```
        for (List list : listOfLists)
         { } 
        ```

    *   在第二个 for-each 循环中，每一行列表中的每一项都将被单独获取

        ```
        for (K item : list)
         { }

        ```

    *   因此，我们可以对这个项目进行任何操作。我们正在打印这个项目。

    下面是上述方法的实现:

    ```
    // Java code to demonstrate the concept of
    // list of lists using loop

    import java.util.*;
    public class List_of_list {

        // Iterate the 2D list using loop
        // and print each element
        public static <K> void
        iterateUsingForEach(List<List<K> > listOfLists)
        {

            // Iterate the 2D list
            // and print each element
            System.out.println("[");

            for (List<K> list : listOfLists) {
                System.out.print("  [");

                for (K item : list) {
                    System.out.print("  "
                                     + item
                                     + ", ");
                }
                System.out.println("], ");
            }
            System.out.println("]");
        }

        // Driver code
        public static void main(String[] args)
        {

            // List of Lists
            ArrayList<List<Integer> > listOfLists
                = new ArrayList<List<Integer> >();

            // Create N lists one by one
            // and append to the list of lists
            List<Integer> list1
                = new ArrayList<Integer>();
            list1.add(5);
            list1.add(10);
            listOfLists.add(list1);

            List<Integer> list2
                = new ArrayList<Integer>();
            list2.add(1);
            listOfLists.add(list2);

            List<Integer> list3
                = new ArrayList<Integer>();
            list3.add(20);
            list3.add(30);
            list3.add(40);
            listOfLists.add(list3);

            // Iterate the 2D list
            iterateUsingForEach(listOfLists);
        }
    }
    ```

    **输出:**

    ```
    [
     [ 5,  10, ], 
     [ 1, ], 
     [ 20,  30,  40, ], 
    ]

    ```

2.  **使用迭代器对列表进行迭代:**
    *   获取迭代的 2D 列表
    *   我们需要两个[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)来成功地迭代 2D 列表。
    *   第一个迭代器将 2D 列表的每一行迭代为一个单独的列表

        ```
        Iterator listOfListsIterator = listOfLists.iterator();

        ```

    *   Each row of the 2D list can be obtained with the help of [next() method of Iterator](https://www.geeksforgeeks.org/how-to-use-iterator-in-java/)

        ```
        listOfListsIterator.next();

        ```

        但是下一个()方法返回迭代器作为对象的对象。因此，我们需要将这个返回的对象转换成一个列表。

        ```
        list = (List)listOfListsIterator.next(); 
        ```

    *   第二个迭代器将分别迭代每行列表中的每一项

        ```
        Iterator eachListIterator = list.iterator();

        ```

    *   因此，我们可以对这个项目进行任何操作。我们正在打印这个项目。

下面是上述方法的实现:

```
// Java code to demonstrate the concept of
// list of lists using iterator

import java.util.*;

class List_of_list {

    // Iterate the 2D list using Iterator
    // and print each element
    public static <K> void
    iterateUsingIterator(List<List<K> > listOfLists)
    {
        // Iterator for the 2D list
        Iterator listOfListsIterator
            = listOfLists.iterator();

        System.out.println("[");
        while (listOfListsIterator.hasNext()) {

            // Type cast next() method
            // to convert from Object to List<K>
            List<K> list = new ArrayList<K>();

            list = (List<K>)listOfListsIterator.next();

            // Iterator for list
            Iterator eachListIterator
                = list.iterator();

            System.out.print("  [");
            while (eachListIterator.hasNext()) {

                System.out.print(
                    "  "
                    + eachListIterator.next()
                    + ", ");
            }
            System.out.println("], ");
        }
        System.out.println("]");
    }

    // Driver code
    public static void main(String[] args)
    {

        // List of Lists
        ArrayList<List<Integer> > listOfLists
            = new ArrayList<List<Integer> >();

        // Create N lists one by one
        // and append to the list of lists
        List<Integer> list1
            = new ArrayList<Integer>();
        list1.add(5);
        list1.add(10);
        listOfLists.add(list1);

        List<Integer> list2
            = new ArrayList<Integer>();
        list2.add(1);
        listOfLists.add(list2);

        List<Integer> list3
            = new ArrayList<Integer>();
        list3.add(20);
        list3.add(30);
        list3.add(40);
        listOfLists.add(list3);

        // Iterate the 2D list
        iterateUsingIterator(listOfLists);
    }
}
```

**输出:**

```
[
 [ 5,  10, ], 
 [ 1, ], 
 [ 20,  30,  40, ], 
]

```