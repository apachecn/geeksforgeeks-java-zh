# Java . util . linked list . index of()、Java 中的 lastindexof()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-linked list-index of-lastindexof-Java/

链表库还提供了**来描述元素**的第一个和最后一个索引，该索引必须分别使用 index of()和 last index of()函数来找到。它们提供了多种多样的方式，因为直接访问在传统的链表中是不可用的，因此了解它是有用的。
T3】1。indexOf(对象 o) : 该方法返回该列表中指定元素的第一个出现的**的**索引**，如果该列表不包含该元素，则返回-1。**

```java
Declaration : 
   public int indexOf(Object o)
Parameters : 
   o :  element to search for
Return Value : 
 This method returns the index of the first occurrence of
 the specified element in this list, or -1 if this list 
 does not contain the element.

```

```java
// Java code to demonstrate the working
// of indexOf(Object o) in linked list
import java.util.*;
public class LinkedListIndexOf {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the initial list
        System.out.println("The initial Linked List is : " + list);

        // Retrieving index of 1st occurrence of "Geeks"
        // Prints 0
        System.out.println("Index of 1st occurrence of Geeks : "
             + list.indexOf("Geeks"));

        // Retrieving index of 1st occurrence of "Astha"
        // Prints -1
        // element not present
        System.out.println("Index of 1st occurrence of Astha : "
             + list.indexOf("Astha"));
    }
}
```

输出:

```java
The initial Linked List is : [Geeks, 4, Geeks, 8]
Index of 1st occurrence of Geeks : 0
Index of 1st occurrence of Astha : -1

```

**2。lastIndexOf(对象 o) :** 此方法返回此列表中指定元素最后一次出现的**的**索引**，如果此列表不包含该元素，则返回-1。**

```java
Declaration : 
  public int lastIndexOf(Object o)
Parameters : 
   o : element to search for
Return Value : 
This method returns the index of the last occurrence 
of the specified element in this list, or -1 if this
list does not contain the element

```

```java
// Java code to demonstrate the working
// of lastIndexOf(Object o) in linked list
import java.util.*;
public class LinkedListLastindexOf {
public static void main(String[] args)
    {
        // Declaring a LinkedList
        LinkedList list = new LinkedList();
        // adding elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);
        // printing the initial list
        System.out.println("The initial Linked List is : " + list);
        // Retrieving index of last occurrence of "Geeks"
        // Prints 2
        System.out.println("Index of last occurrence of Geeks : " 
            + list.lastIndexOf("Geeks"));

        // Retrieving index of last occurrence of "Astha"
        // Prints -1
        // element not present
        System.out.println("Index of last occurrence of Astha : " 
            + list.lastIndexOf("Astha"));
    }
}
```

输出:

```java
The initial Linked List is : [Geeks, 4, Geeks, 8]
Index of last occurrence of Geeks : 2
Index of last occurrence of Astha : -1

```

**实际应用:**由于这两个函数都显示特定数字或字符串等的第一个和最后一个索引，因此它们可以用于**计算在**值的最后一个和第一个出现之间出现的元素、人员等的数量。下面给出一个小例子。

```java
// Java code to demonstrate the application
// of indexOf() in linked list
import java.util.*;
public class LinkedListIndexApp {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding elements to check
        list.add(1);
        list.add(4);
        list.add(3);
        list.add(6);
        list.add(7);
        list.add(4);
        list.add(8);

        // printing the initial list
        System.out.println("The initial Linked List is : " + list);

        // computing result
        int res = list.lastIndexOf(4) - list.indexOf(4) - 1;

        // Printing the number of elements between 1st occurrence of 4 and last 4
        // prints 3
        System.out.println("The no. between 4s are :  " + res);
    }
}
```

输出:

```java
The initial Linked List is : [1, 4, 3, 6, 7, 4, 8]
The no. between 4s are :  3

```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。