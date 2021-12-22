# Java 中的 Java.util.ArrayList.addall()方法

> 原文:[https://www . geesforgeks . org/Java-util-ArrayList-addall-method-Java/](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/)

下面是 Java 中 [**ArrayList**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **addAll()** 方法:

1.  **布尔 addAll(Collection c) :** 这个方法按照指定集合的迭代器返回元素的顺序，将指定集合中的所有元素追加到这个列表的末尾。如果在操作过程中修改了指定的集合，则此操作的行为是未定义的(意味着如果指定的集合是此列表，并且此列表是非空的，则此调用的行为是未定义的)。

    ```
    Parameters:
    c : This is the collection containing elements to be added to this list.
    Exception:
    NullPointerException : If the specified collection is null
    ```

    ```
    // Java program to illustrate
    // boolean addAll(Collection c)
    import java.io.*;
    import java.util.ArrayList;

    public class ArrayListDemo {
        public static void main(String args[])
        {

            // create an empty array list1 with initial 
            // capacity as 5
            ArrayList<Integer> arrlist1 = 
                               new ArrayList<Integer>(5);

            // use add() method to add elements in the list
            arrlist1.add(12);
            arrlist1.add(20);
            arrlist1.add(45);

            // prints all the elements available in list1
            System.out.println("Printing list1:");
            for (Integer number : arrlist1) 
                System.out.println("Number = " + number);        

            // create an empty array list2 with an initial
            // capacity
            ArrayList<Integer> arrlist2 = 
                                 new ArrayList<Integer>(5);

            // use add() method to add elements in list2
            arrlist2.add(25);
            arrlist2.add(30);
            arrlist2.add(31);
            arrlist2.add(35);

            // let us print all the elements available in 
            // list2
            System.out.println("Printing list2:");
            for (Integer number : arrlist2) 
                System.out.println("Number = " + number);        

            // inserting all elements, list2 will get printed
            // after list1
            arrlist1.addAll(arrlist2);

            System.out.println("Printing all the elements");
            // let us print all the elements available in 
            // list1
            for (Integer number : arrlist1) 
                System.out.println("Number = " + number);        
        }
    }
    ```

    ```
    Output:Printing list1:
    Number = 12
    Number = 20
    Number = 45
    Printing list2:
    Number = 25
    Number = 30
    Number = 31
    Number = 35
    Printing all the elements
    Number = 12
    Number = 20
    Number = 45
    Number = 25
    Number = 30
    Number = 31
    Number = 35

    ```

    **布尔 addAll(int index，Collection c):** 此方法从指定位置开始，将指定集合中的所有元素插入此列表。它将当前在该位置的元素(如果有)和任何后续元素向右移动(增加它们的索引)。新元素将按照指定集合的迭代器返回的顺序出现在列表中。

    ```
    Parameters:
    index : The index at which to insert the first element from the specified collection.
    c : This is the collection containing elements to be added to this list.
    Exception:
    IndexOutOfBoundsException : If the index is out of range
    NullPointerException : If the specified collection is null
    ```

    ```
    // Java program to illustrate
    // boolean addAll(int index, Collection c)
    import java.io.*;
    import java.util.ArrayList;

    public class ArrayListDemo {
        public static void main(String args[])
        {

            // create an empty array list1 with initial
            // capacity 5
            ArrayList<Integer> arrlist = 
                            new ArrayList<Integer>(5);

            // using add() method to add elements in the 
            // list
            arrlist.add(12);
            arrlist.add(20);
            arrlist.add(45);

            // prints all the elements available in list1
            System.out.println("Printing list1:");
            for (Integer number : arrlist) 
                System.out.println("Number = " + number);        

            // create an empty array list2 with an initial
            // capacity
            ArrayList<Integer> arrlist2 = 
                                new ArrayList<Integer>(5);

            // use add() method to add elements in list2
            arrlist2.add(25);
            arrlist2.add(30);
            arrlist2.add(31);
            arrlist2.add(35);

            // prints all the elements available in list2
            System.out.println("Printing list2:");
            for (Integer number : arrlist2) 
                System.out.println("Number = " + number);        

            // inserting all elements of list2 at third 
            // position
            arrlist.addAll(2, arrlist2);

            System.out.println("Printing all the elements");

            // prints all the elements available in list1
            for (Integer number : arrlist) 
                System.out.println("Number = " + number);        
        }
    }
    ```

    ```
    Output:Printing list1:
    Number = 12
    Number = 20
    Number = 45
    Printing list2:
    Number = 25
    Number = 30
    Number = 31
    Number = 35
    Printing all the elements
    Number = 12
    Number = 20
    Number = 25
    Number = 30
    Number = 31
    Number = 35
    Number = 45

    ```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。