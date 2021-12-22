# Java.util.LinkedList.offer()、offerFirst()、offerLast()在 Java 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-linklist-offers-offers rst-offers rlast-Java/

链表还有一个功能，完成**元素的灵活添加**的工作，并帮助在列表的前面和后面进行添加，这些功能字面上“提供”设施，并命名为 offer()。有三种类型可供选择，本文将在下面讨论。

**1。offer(E e) :** 此方法添加**指定元素作为此列表的尾部**(最后一个元素)。

```java
Declaration : 
   public boolean offer(E e)
Parameters : 
    e: the element to add
Return Value : 
     This method returns true 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate the working
// of offer(E e) in linked list
import java.util.*;
public class LinkedListoffer1 {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked list is : " + list);

        // offering a new element
        // adds element at tail.
        list.offer("Astha");

        // printing the new list
        System.out.println("LinkedList after insertion using offer() : " + list);
    }
}
```

输出:

```java
The initial Linked list is : [Geeks, 4, Geeks, 8]
LinkedList after insertion using offer() : [Geeks, 4, Geeks, 8, Astha]
```

**2。offerFirst(E e) :** 这个方法**在这个列表的前面**插入指定的元素**。**

```java
Declaration : 
   public boolean offerFirst(E e)
Parameters : 
    e : the element to add
Return Value :  
    This method returns true
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate the working
// of offerFirst(E e) in linked list
import java.util.*;
public class LinkedListOfferFirst {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked list is : " + list);

        // offering a new element
        // adds element at head.
        list.offerFirst("Astha");

        // printing the new list
        System.out.println("LinkedList after insertion using offerFirst() : " + list);
    }
}
```

输出:

```java
The initial Linked list is : [Geeks, 4, Geeks, 8]
LinkedList after insertion using offerFirst() : [Astha, Geeks, 4, Geeks, 8]
```

**3。offerLast(E e) :** 此方法**在此列表的末尾**插入指定元素**。**

```java
Declaration : 
     public boolean offerLast(E e)
Parameters : 
    e:the element to add
Return Value : 
    This method returns true
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate the working
// of offerLast(E e) in linked list
import java.util.*;
public class LinkedListOfferLast {

public static void main(String[] args)
    {

        // Declaring a LinkedList
        LinkedList list = new LinkedList();

        // adding elements
        list.add("Geeks");
        list.add(4);
        list.add("Geeks");
        list.add(8);

        // printing the list
        System.out.println("The initial Linked list is : " + list);

        // offering a new element
        // adds element at end.
        list.offerLast("Astha");

        // printing the new list
        System.out.println("LinkedList after insertion using offerLast() : " + list);
    }
}
```

输出:

```java
The initial Linked list is : [Geeks, 4, Geeks, 8]
LinkedList after insertion using offerLast() : [Geeks, 4, Geeks, 8, Astha]
```

**实际应用:**在队列中**优先级增加的情况下，可以实现这些功能的这种“灵活增加”的质量，其中大于阈值的元素必须在小于阈值的元素之前处理。下面的一小段代码讨论了这一点。**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate the application
// of offer() in linked list
import java.util.*;
public class LinkedListOfferLast {

public static void main(String[] args)
    {

        // Declaring LinkedLists
        LinkedList<Integer> list = new LinkedList<Integer>();
        LinkedList prioList = new LinkedList();

        // adding elements
        list.add(12);
        list.add(4);
        list.add(8);
        list.add(10);
        list.add(3);
        list.add(15);

        // declaring threshold
        int thres = 10;

        // printing the list
        System.out.println("The initial Linked list is : " + list);

        while (!list.isEmpty()) {

            int t = list.poll();

            // adding >=10 numbers at front rest at back
            if (t >= 10)
                prioList.offerFirst(t);
            else
                prioList.offerLast(t);
        }

        // The resultant list is
        System.out.println("The prioritized Linked list is : " + prioList);
    }
}
```

输出:

```java
The initial Linked list is : [12, 4, 8, 10, 3, 15]
The prioritized Linked list is : [15, 10, 12, 4, 8, 3]
```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。