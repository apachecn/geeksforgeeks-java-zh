# Java 中的 Java . util . collections . frequency()

> 原文:[https://www . geesforgeks . org/Java-util-collections-frequency-Java-examples/](https://www.geeksforgeeks.org/java-util-collections-frequency-java-examples/)

**java.util.Collections . frequency()**方法存在于 Java . util . collections 类中。它用于获取元素在集合的指定列表中出现的频率。更正式地说，它返回集合中元素 e 的数量。

**语法**

```java
public static int frequency(Collection<?> c, Object o)
Parameters : 
c - the collection in which to determine the frequency of o
o - the object whose frequency is to be determined
Returns :
Returns the number of elements in the specified collection 
equal to the specified object.
Throws:
NullPointerException - if c is null

```

```java
// Java program to demonstrate working of 
// java.utils.Collections.frequency()

import java.util.*;

public class FrequencyDemo
{
    public static void main(String[] args)
    {
        // Let us create a list of strings
        List<String>  mylist = new ArrayList<String>();
        mylist.add("practice");
        mylist.add("code");
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");

        // Here we are using frequency() method
        // to get  frequency of element "code"
        int freq = Collections.frequency(mylist, "code");

        System.out.println(freq);
    }
}
```

输出:

```java
2

```

**如何在 Java 中快速获取数组中某个元素的频率？**

[Java 中的数组类](https://www.geeksforgeeks.org/array-class-in-java/)没有频率方法。但是我们也可以使用 Collections.frequency()来获取数组中元素的频率。

```java
// Java program to get frequency of an element 
//  with java.utils.Collections.frequency()

import java.util.*;

public class FrequencyDemo
{
    public static void main(String[] args)
    {
        // Let us create an array of integers
        Integer arr[] = {10, 20, 20, 30, 20, 40, 50};

        // Please refer below post for details of asList()
        // https://www.geeksforgeeks.org/array-class-in-java/
        int freq = Collections.frequency(Arrays.asList(arr), 20);

        System.out.println(freq);
    }
}
```

输出:

```java
3

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。