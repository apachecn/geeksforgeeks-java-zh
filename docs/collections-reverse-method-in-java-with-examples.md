# Collections.reverse()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/collections-reverse-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-reverse-method-in-java-with-examples/)

**reverse()**Collections 类的方法(顾名思义)用于反转存储元素的对象中的元素。它颠倒了作为参数传递的列表中元素的顺序。这个类存在于 java.util 包中，所以做语法如下:

```java
import java.util.Collections;
```

```java
Collections.reverse(class_obj);
```

**插图:**

```java
Input  : {1, 2, 3, 4}
Output : {4, 3, 2, 1}
```

**参数:**元素要反转的类的对象。

```java
public static void reverse(List myList)
```

**抛出异常:**如果指定列表或其列表迭代器不支持 set 操作，则抛出*不支持操作异常*。

让我们通过下面列出的用例来看看这个方法的用法:

*   Invert an array list
*   Invert a linked list
*   Invert an array

让我们通过在族 java 代码中实现 Collections 类的这个方法，如下所示:

**案例 1:** 反转数组列表

T5】JAVAT7

```java
// Java program to illustrate reverse() method
// of Collections class over ArrayList

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Let us create a list of strings
        List<String> mylist = new ArrayList<String>();

        // Adding elements to the List
        // Custom input elements
        mylist.add("practice");
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");

        // Print all elements originally
        System.out.println("Original List : " + mylist);

        // Using reverse() method to
        // reverse the element order of mylist
        Collections.reverse(mylist);

        // Print all elements of list in reverse order
        // using reverse() method
        System.out.println("Modified List: " + mylist);
    }
}
```

T8T10**输出**T1

**案例 2:** 反转链接列表

T5】JavaT7

```java
// Java program to illustrate reverse() method
// of Collections class over ArrayList

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Let us create a list of strings
        List<String> mylist = new LinkedList<String>();

        // Adding elements to the List
        // Custom input elements
        mylist.add("practice");
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");

        // Print all elements originally
        System.out.println("Original List : " + mylist);

        // Using reverse() method to
        // reverse the element order of mylist
        Collections.reverse(mylist);

        // Print all elements of list in reverse order
        // using reverse() method
        System.out.println("Modified List: " + mylist);
    }
}
```

T8T10**输出**T1

如果我们浏览一下上面的程序，那么只有一个微小的签名细节，那就是我们正在创建一个 LinkedList 类的对象，而不是 Array 类，如示例 1A 所示。对于 LinkedList，我们只是在上面的代码中进行了如下所示的更改:

```java
LinkedList in "List mylist = new ArrayList();".
```

**情况 3:** 反转数组:[Java 中的 Arrays 类](https://www.geeksforgeeks.org/array-class-in-java/)没有反转方法。我们可以使用 Collections.reverse()来反转数组，如下所示:

**示例**

## Java

```java
// Java program to Illustrate Reversal of Array
// using reverse() method of Collections class

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating input integer array
        Integer arr[] = { 10, 20, 30, 40, 50 };

        // Print elements of array
        System.out.println("Original Array : "
                           + Arrays.toString(arr));

        // Reversing elements of array using reverse()
        // method of Arrays class and fetching as
        // list via asList()
        Collections.reverse(Arrays.asList(arr));

        // Print and display reverse updated array
        System.out.println("Modified Array : "
                           + Arrays.toString(arr));
    }
}
```

**输出**

```java
Original Array : [10, 20, 30, 40, 50]
Modified Array : [50, 40, 30, 20, 10]
```

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。