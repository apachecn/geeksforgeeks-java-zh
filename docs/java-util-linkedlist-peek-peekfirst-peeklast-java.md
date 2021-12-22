# Java . util . LinkedIn . peek()、peekfirst()、peeklast()在 Java

中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-link list-peek-peek IRST-peek klat-Java/

链表类提供了“T0”查看列表的第一个和最后一个元素的功能，因此在只需要**检索而不一定需要删除的情况下会很有用。本文介绍并讨论了三种功能。

**1。peek() :** 此方法**检索，但不移除**，即此列表的头部(第一个元素)。**

```java
Declaration : 
   public E peek()
Return Value : 
  This method returns the head of this list, or null if this list is empty.

```

```java
// Java code to demonstrate the working
// of peek() in LinkedList
import java.util.*;
public class LinkedPeek1 {

public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add("8");

        // printing the list
        System.out.println("The initial list is :" + list);

        // peek at the head of the list
        // Prints 1st element, "Geeks"
        System.out.println("Head of the list : " + list.peek());
    }
}
```

输出:

```java
The initial list is :[Geeks, 4, Geeks, 8]
Head of the list : Geeks

```

**2。peekFirst() :** 这个方法**检索，但是不移除**，这个列表的第一个元素，或者如果这个列表是空的，返回 null。这类似于 peek()。

```java
Declaration : 
   public E peekFirst()
Return Value : 
    This method returns the first element of this list, or null if this list is empty

```

```java
// Java code to demonstrate the working
// of peekFirst() in LinkedList
import java.util.*;
public class LinkedPeek2 {

public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add("8");

        // printing the list
        System.out.println("The initial list is :" + list);

        // peek at the first element of the list
        // Prints 1st element, "Geeks"
        System.out.println("First element of the list is : " + list.peekFirst());
    }
}
```

输出:

```java
The initial list is :[Geeks, 4, Geeks, 8]
First element of the list is : Geeks

```

**3。peekLast() :** 此方法**检索**，但不移除此列表的**最后一个元素**，如果此列表为空，则返回 null。

```java
Declaration
  public E peekLast()
Return Value
   This method returns the last element of this list, or null if this list is empty

```

```java
// Java code to demonstrate the working
// of peekLast() in LinkedList
import java.util.*;
public class LinkedPeek3 {

public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial list is :" + list);

        // peek at the last element of the list
        // Prints last element, 8
        System.out.println("Last element of the list is : " + list.peekLast());
    }
}
```

输出:

```java
The initial list is :[Geeks, 4, Geeks, 8]
Last element of the list is : 8

```

**实际应用:**可以想到的实际应用是，这可以用于潜在的纸牌游戏中，其中**个人可以在询问他们想要看哪一个元素时偷看纸牌的第一个或最后一个元素**。下面的代码解释了工作原理。

```java
// Java code to demonstrate the application
// of peek()
import java.util.*;
public class LinkedPeekApp {

public static void main(String[] args)
    {

        // declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding  elements in deck
        list.add(5);
        list.add(4);
        list.add("Jack");
        list.add(8);
        list.add("King");

        // printing the list
        System.out.println("The initial deck is :" + list);

        String d = "upper";

        System.out.println("The element chosen to peek is : " + d);

        if (d == "upper")
            System.out.println("The Upper element is : " + list.peekFirst());
        else
            System.out.println("The Lower element is : " + list.peekLast());
    }
}
```

输出:

```java
The initial deck is :[5, 4, Jack, 8, King]
The element chosen to peek is : upper
The Upper element is : 5

```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。