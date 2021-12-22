# Java 中的 Java.util.ArrayList.add()方法

> 原文:[https://www . geesforgeks . org/Java-util-ArrayList-add-method-Java/](https://www.geeksforgeeks.org/java-util-arraylist-add-method-java/)

下面是 Java 中 [**ArrayList**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 add()方法:

1.  **布尔 add(Object o)** :这个方法在这个列表的末尾追加指定的元素。

    ```java
    Parameters:    
    object o: The element to be appended to this list.
    Exception: NA
    ```

    ```java
    // Java code to illustrate add(Object o)
    import java.io.*;
    import java.util.ArrayList;

    public class ArrayListDemo {
    public static void main(String[] args)
        {

            // create an empty array list with an initial capacity
            ArrayList<Integer> arrlist = new ArrayList<Integer>(5);

            // use add() method to add elements in the list
            arrlist.add(15);
            arrlist.add(20);
            arrlist.add(25);

            // prints all the elements available in list
            for (Integer number : arrlist) {
                System.out.println("Number = " + number);
            }
        }
    }
    ```

    输出:

    ```java
    Number = 15
    Number = 20
    Number = 25

    ```

2.  **void add(int index，Object element)** :此方法在此列表的指定位置插入指定元素 E。它会将当前在该位置的元素(如果有)和任何后续元素向右移动(将一个元素添加到它们的索引中)。

    ```java
    Parameters:
    index : The index at which the specified element is to be inserted.
    element : The element to be inserted.

    Exception:
    Throws IndexOutOfBoundsException if the specified
    index is out of range (index  size()).
    ```

    ```java
    // Java code to illustrate
    // void add(int index, Object element)
    import java.io.*;
    import java.util.ArrayList;

    public class ArrayListDemo {
    public static void main(String[] args)
        {

            // create an empty array list with an initial capacity
            ArrayList<Integer> arrlist = new ArrayList<Integer>(5);

            // use add() method to add elements in the list
            arrlist.add(10);
            arrlist.add(22);
            arrlist.add(30);
            arrlist.add(40);

            // adding element 35 at fourth position
            arrlist.add(3, 35);

            // let us print all the elements available in list
            for (Integer number : arrlist) {
                System.out.println("Number = " + number);
            }
        }
    }
    ```

    输出:

    ```java
    Number = 10
    Number = 22
    Number = 30
    Number = 35
    Number = 40

    ```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。