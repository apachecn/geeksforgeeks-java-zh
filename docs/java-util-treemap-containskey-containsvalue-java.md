# Java . util . treemap . contains key()和 containsValue()在 Java 中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-tree map-containskey-containsvalue-Java/

Java.util.TreeMap 中有两个 contains()的**和**变体，本文将对这两个变体进行讨论。

**1。containskey(对象 o) :** 如果映射包含指定键的映射，则返回 true。

```
Parameters:
o : The key which will be tested whether present or not.
Return Value:
Returns true if there is a mapping for the given key.
Exception:
ClassCastException : This is thrown if the given key cannot be compared
with the keys currently in the map.
NullPointerException : This is thrown if the specified key is null.

```

```
// Java code to demonstrate the working
// of containsKey()

import java.io.*;
import java.util.*;

public class containsKey {
public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        treemap.put(2, "two");
        treemap.put(7, "seven");
        treemap.put(3, "three");
        treemap.put(6, "six");
        treemap.put(9, "nine");

        // Use of containsKey
        // returns true if mapping for the number is present
        System.out.println(treemap.containsKey(6));
        System.out.println(treemap.containsKey(4));
    }
}
```

输出:

```
true
false

```

**2。containsValue(对象 o) :** 如果此映射将一个或多个键映射到指定值，则返回 true。

```
Parameters:
o : This is the value whose presence in this map is to be tested.
Return Value:
Returns true if a mapping to this value exists else false. Exception:
NA

```

```
// Java code to demonstrate the working
// of containsValue()

import java.io.*;
import java.util.*;

public class containsValue {
public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> treemap = new TreeMap<Integer, String>();

        // assigning the values in the tree map
        // using put()
        treemap.put(2, "two");
        treemap.put(7, "seven");
        treemap.put(3, "three");
        treemap.put(6, "six");
        treemap.put(9, "nine");

        // Use of containsValue
        // returns true if more than one keys are mapped
        System.out.println(treemap.containsValue("six"));
        System.out.println(treemap.containsValue("four"));
    }
}
```

输出:

```
true
false

```

本文由**香巴拉维·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。