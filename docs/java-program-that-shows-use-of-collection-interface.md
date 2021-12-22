# 显示使用收集界面的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-显示集合使用的程序-界面/](https://www.geeksforgeeks.org/java-program-that-shows-use-of-collection-interface/)

[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)是用于表示和操纵集合的统一架构，使得集合能够独立于实现细节而被操纵。

**采集框架的用途及优势:**

*   这通过提供数据结构和算法减少了程序员的工作量，因此我们不必编写它们。
*   这通过提供数据结构和算法的高性能实现来提高性能。
*   这通过建立一种通用语言来来回传递集合，从而提供了不相关的 API 之间的互操作性。
*   通过要求您学习多个临时集合 API，减少了学习 API 所需的工作量。
*   这提供了对集合执行有用功能的静态方法，例如对列表进行排序。
*   这提供了向其他实现添加功能(如同步)的包装器实现。

它为我们利用和解决发展问题提供了更多的优势。

**用法:**不同类型接口的示例如下:

1.  **列表界面**
2.  **喜欢列表**
3.  **地图界面**
4.  **堆叠**

**用例 1:** 列表界面

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program that Shows Use of Collection Interface
// ArrayList

import java.util.*;

class GFG {
    public static void main(String args[])
    {
        ArrayList<String> list = new ArrayList<String>();
        list.add("Geeks");
        list.add("areyou");
        list.add("working");
        list.add("hard?");

        Iterator itr = list.iterator();
        while (itr.hasNext()) {
            System.out.println(itr.next());
        }
    }
}
```

**Output**

```
Geeks
areyou
working
hard?
```

**用例 2:** 链表

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program that Shows Use of Collection Interface
// LinkedList

import java.util.*;

// Class testing java Collection
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a LinkedList
        LinkedList<String> al = new LinkedList<String>();

        // Adding elements to above linked list
        al.add("Geeks");
        al.add("areyou");
        al.add("working");
        al.add("hard?");

        // Iterator
        Iterator<String> itr = al.iterator();

        // Condition check over elements inside using
        // hasNext() method which holds true till there is
        // element inside list
        while (itr.hasNext()) {

            // Printing elements of LinkedList
            System.out.println(itr.next());
        }
    }
}
```

**Output**

```
Geeks
areyou
working
hard?
```

**用例 3:** 映射接口

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program that Shows Use of Collection Interface
// Hash-Map

import java.util.*;
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating a Map
        Map<Integer, String> map = new HashMap<>();

        // Adding elements to map
        map.put(1, "Geeks");
        map.put(2, "are");
        map.put(3, "you");
        map.put(4, "working");

        // Traversing Map
        // Converting to Set so that traversal is accessed
        Set set = map.entrySet();

        // Iterator
        Iterator itr = set.iterator();

        // Condition check over elements inside using
        // hasNext() method which holds true till there is
        // element inside list

        while (itr.hasNext()) {
            // Converting to Map.Entry so that we can get
            // key and value separately

            Map.Entry entry = (Map.Entry)itr.next();

            // Printing elements inside HashMap
            System.out.println(entry.getKey() + " "
                               + entry.getValue());
        }
    }
}
```

**Output**

```
1 Geeks
2 are
3 you
4 working
```

**用例 4:** 栈

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program that Shows Use of Collection Interface
// Stack

import java.util.*;
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a stack in memory
        Stack<String> stack = new Stack<String>();

        // Adding elements to stack
        stack.push("Geeks");
        stack.push("are");
        stack.push("you");
        stack.push("working");
        stack.push("hard?");

        // pop() returns all elements of stack
        stack.pop();

        //. iterator
        Iterator<String> itr = stack.iterator();

        // Condition check over elements inside using
        // hasNext() method which holds true till there is
        // element inside list
        while (itr.hasNext()) {

            // Print all popped elements
            System.out.println(itr.next());
        }
    }
}
```

**Output**

```
Geeks
are
you
working
```