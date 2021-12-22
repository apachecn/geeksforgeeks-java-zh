# Java 中的 Java . util . collections . unjoint()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-util-collections-disjoint-method-Java-examples/](https://www.geeksforgeeks.org/java-util-collections-disjoint-method-java-examples/)

**java.util.Collections . distance()**方法存在于 Java . util . collections 类中。它用于检查两个指定的集合是否不相交。更正式地说，如果两个集合没有共同的元素，它们就是不相交的。

```java
Syntax:
public static boolean disjoint(Collection<?> c1, Collection<?> c2)
Parameters : 
c1 - a collection
c2 - a collection
Returns :
true if the two specified collections have no elements in common.
Throws:
NullPointerException - if either collection is null.
NullPointerException - if one collection contains a null element and null is not an eligible 
element for the other collection.
ClassCastException - if one collection contains an element that is of a type which is ineligible
 for the other collection.

```

请注意，允许在两个参数中传递相同的集合，在这种情况下，当且仅当集合为空时，该方法将返回 **true。**

```java
// Java program to demonstrate working of 
// java.utils.Collections.disjoint()

import java.util.*;

public class DisjointDemo
{
    public static void main(String[] args)
    {
        // Let us create array list of strings
        List<String>  mylist1 = new ArrayList<String>();
        mylist1.add("practice");
        mylist1.add("code");
        mylist1.add("quiz");
        mylist1.add("geeksforgeeks");

        // Let us create vector of strings
        List<String>  mylist2 = new Vector<String>();
        mylist2.add("geeks");
        mylist2.add("geek");
        mylist2.add("for");
        mylist2.add("coder");

        // Let us create a vector 
        List mylist3 = new Vector();

        mylist3.add(1); 
        mylist3.add("practice");     

        // Let us create a Set of strings
        Set<String>  mylist4 = new HashSet<String>();
        mylist4.add("practice");
        mylist4.add("code");
        mylist4.add("quiz");
        mylist4.add("geeksforgeeks");

        // Here we are using disjoint() method to check 
        // whether two collections are disjoint or not
        System.out.println("is mylist1 disjoint to mylist2 : " +
                            Collections.disjoint(mylist1, mylist2));

        System.out.println("is mylist1 disjoint to mylist3 : " +
                            Collections.disjoint(mylist1, mylist3));

        System.out.println("is mylist1 disjoint to mylist4 : " +
                            Collections.disjoint(mylist1, mylist4));

    }
}
```

输出:

```java
is mylist1 disjoint to mylist2 : true
is mylist1 disjoint to mylist3 : false
is mylist1 disjoint to mylist4 : false

```

**如何快速检查 Java 中两个数组是否不相交？**

[Java 中的数组类](https://www.geeksforgeeks.org/array-class-in-java/)没有不相交的方法。我们可以使用 Collections.disjoint()来快速检查两个数组的分离。

```java
// Java program to demonstrate disjoint 
// method with arrays

import java.util.*;

public class DisjointDemo
{
    public static void main(String[] args)
    {
        // Let us create  arrays of integers
        Integer arr1[] = {10, 20, 30, 40, 50};
        Integer arr2[] = {60, 70, 80, 90, 100};
        Integer arr3[] = {50, 70, 80, 90, 100};
        Double  arr4[] = {50.0, 60.0, 110.0};

        // Please refer below post for details of asList()
        // https://www.geeksforgeeks.org/array-class-in-java/
        // Here we are using disjoint() method to check 
        // whether two arrays are disjoint or not
        System.out.println("is arr1 disjoint to arr2 : " +
                         Collections.disjoint(Arrays.asList(arr1), Arrays.asList(arr2)));

        System.out.println("is arr1 disjoint to arr3 : " +
                         Collections.disjoint(Arrays.asList(arr1), Arrays.asList(arr3)));

        System.out.println("is arr1 disjoint to arr4 : " +
                         Collections.disjoint(Arrays.asList(arr1), Arrays.asList(arr4)));

    }
}
```

输出:

```java
is arr1 disjoint to arr2 : true
is arr1 disjoint to arr3 : false
is arr1 disjoint to arr4 : true

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。