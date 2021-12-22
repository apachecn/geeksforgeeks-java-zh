# Java 中的 Java.util.Collections.rotate()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-util-collections-rotate-method-Java-examples/](https://www.geeksforgeeks.org/java-util-collections-rotate-method-java-examples/)

**java.util.Collections . rotate()**方法存在于 Java . util . collections 类中。它用于将集合的指定列表中的元素旋转给定的距离。

```
Syntax:
public static void rotate(List< type > list, int distance)
Parameters : 
list - the list to be rotated.
distance - the distance to rotate the list. 
type - Type of list to be rotated. Examples of 
       types are Integer, String, etc.
Returns :
NA
Throws:
UnsupportedOperationException - if the specified list or 
its list-iterator does not support the set operation.

```

距离值没有限制。它可以是零、负数或大于 list.size()。调用此方法后，对于介于 0 和 list.size()-1 之间的 I 的所有值，索引 I 处的元素将是先前索引(I–distance)mod list . size()处的元素。

```
// Java program to demonstrate working of 
// java.utils.Collections.rotate()

import java.util.*;

public class RotateDemo
{
    public static void main(String[] args)
    {
        // Let us create a list of strings
        List<String>  mylist = new ArrayList<String>();
        mylist.add("practice");
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");

        System.out.println("Original List : " + mylist);

        // Here we are using rotate() method
        // to rotate the element by distance 2
        Collections.rotate(mylist, 2);

        System.out.println("Rotated List: " + mylist);
    }
}
```

输出:

```
Original List : [practice, code, quiz, geeksforgeeks]
Rotated List: [quiz, geeksforgeeks, practice, code]

```

**如何使用 rotate()在 Java 中快速旋转数组？**

[Java 中的数组类](https://www.geeksforgeeks.org/array-class-in-java/)没有旋转方法。我们也可以使用 Collections.rotate()来快速旋转数组。

```
// Java program to demonstrate rotation of array
// with Collections.rotate()
import java.util.*;

public class RotateDemo
{
    public static void main(String[] args)
    {
        // Let us create an array of integers
        Integer arr[] = {10, 20, 30, 40, 50};

        System.out.println("Original Array : " +
                                Arrays.toString(arr));

        // Please refer below post for details of asList()
        // https://www.geeksforgeeks.org/array-class-in-java/
        // rotating an array by distance 2
        Collections.rotate(Arrays.asList(arr), 2);

        System.out.println("Modified Array : " +
                                Arrays.toString(arr));
    }
}
```

输出:

```
Original Array : [10, 20, 30, 40, 50]
Modified Array : [40, 50, 10, 20, 30]

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。