# Java.util.LinkedList.get()、getFirst()、getlast()中的 Java

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-linklist-get-first-get ast-Java/

允许**获取特定索引**处的元素的常规方法是获取()。虽然在 LinkedList 中，如果没有完整的遍历，永远不可能实现这一点，但是这个方法允许同样的情况。这里有三种变体，所有这些都将在本文中讨论，当然也有例外。
T3】1。get(int index) : 该方法返回列表中**指定位置**的元素。

```
Declaration : 
    public E get(int index)
Parameters : 
    index :  index of the element to return
Return Value : 
   This method returns the element at the specified position in this list
Exception
     IndexOutOfBoundsException : if the index is out of range

```

```
// Java code to demonstrate the working
// of get(int index) in linked list
import java.util.*;
public class LinkedListget1 {
public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // adding elements using add()
        list.add("Geeks");
        list.add("4");
        list.add("Geeks");
        list.add("8");

        // printing the whole list
        System.out.println("The elements in List are : " + list);

        // using get() to print element at index 3
        // prints 8
        System.out.println("Element at index 3 is : " + list.get(3));
    }
}
```

输出:

```
The elements in List are : [Geeks, 4, Geeks, 8]
Element at index 3 is : 8

```

**2。getFirst() :** 这个方法返回这个列表中的第一个**元素。**

```
Declaration : 
    public E getFirst()
Return Value : 
    This method returns the first element in this list
Exceptions : 
     NoSuchElementException : if this list is empty

```

```
// Java code to demonstrate the working
// of getFirst() in linked list
import java.util.*;
public class LinkedListget2 {
public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // adding elements using add()
        list.add("Geeks");
        list.add("4");
        list.add("Geeks");
        list.add("8");

        // printing the whole list
        System.out.println("The elements in List are : " + list);

        // using get() to print element at first index
        // prints "Geeks"
        System.out.println("Element at 1st index is : " + list.getFirst());
    }
}
```

输出:

```
The elements in List are : [Geeks, 4, Geeks, 8]
Element at 1st index is : Geeks

```

**3。getLast() :** 这个方法返回这个列表中最后一个**元素。**

```
Declaration : 
    public E getLast()
Return Value : 
   This method returns the last element in this list
Exceptions : 
   NoSuchElementException : if this list is empty

```

```
// Java code to demonstrate the working
// of getLast() in linked list
import java.util.*;
public class LinkedListget3 {
public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // adding elements using add()
        list.add("Geeks");
        list.add("4");
        list.add("Geeks");
        list.add("8");

        // printing the whole list
        System.out.println("The elements in List are : " + list);

        // using get() to print element at last index
        // prints "8"
        System.out.println("Element at last index is : " + list.getLast());
    }
}
```

输出:

```
The elements in List are : [Geeks, 4, Geeks, 8]
Element at last index is : 8

```

**Exceptions**

**1 .IndexOutOfBoundException**

```
// Java code to demonstrate the Exceptions
// of get()
import java.util.*;
public class LinkedListExcep1 {
public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // adding elements using add()
        list.add("Geeks");
        list.add("4");
        list.add("Geeks");
        list.add("8");

        // Trying to get element at index 7
        // throws exception
        System.out.println("The element at index 7 is : " + list.get(7));
    }
}
```

输出:

```
No Output

```

运行时错误:

```
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 7, Size: 4
    at java.util.LinkedList.checkElementIndex(LinkedList.java:555)
    at java.util.LinkedList.get(LinkedList.java:476)
    at LinkedListExcep1.main(LinkedListExcep1.java:22)

```

**2 .nosuchinelement exception**

```
// Java code to demonstrate the Exceptions
// of getFirst()
import java.util.*;
public class LinkedListExcep2 {
public static void main(String[] args)
    {
        // declaring a LinkedList
        LinkedList<String> list = new LinkedList<String>();

        // Trying to get first element at index 7
        // throws exception
        System.out.println("The first element of list is : " + list.getFirst());
    }
}
```

输出:

```
No Output

```

运行时错误:

```
Exception in thread "main" java.util.NoSuchElementException
    at java.util.LinkedList.getFirst(LinkedList.java:244)
    at LinkedListExcep2.main(LinkedListExcep2.java:15)

```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。