# Java 中的 Java.util.TreeMap.put()和 putAll()

> 原文:[https://www . geesforgeks . org/Java-util-tree map-put-putall-Java/](https://www.geeksforgeeks.org/java-util-treemap-put-putall-java/)

TreeMap 中的插入是使用 put 函数的变体来处理的。Java.util.TreeMap 中有两个 put()的**和**变体，本文将对这两个变体进行讨论。

**1。put() :** 它将**指定值与地图中的指定键**相关联。如果一个键已经存在，那么更新它会导致该键的更新。

```
Parameters:
key : The key with which the value is to be associated.
value : The value to be associated with the given key.
Return Value:
It returns the previously associated value with this key,
or null if there was no mapping for key.
Exception:
Not Available.

```

```
// Java code demonstrating the working
// of put()
import java.io.*;
import java.util.*;
public class Put {
    public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<String, Integer> tmp = new TreeMap<String, Integer>();

        // assigning the values in the tree map
        // using put()
        tmp.put("one", 1);
        tmp.put("two", 3);

        // Printing initial TreeMap
        System.out.println("The initial TreeMap is : " + tmp);

        // Putting value at key two
        // replaces the previous value if present
        int z = tmp.put("two", 2);

        // checking the previous value associated with "two"
        System.out.println("The previous value with two is : " + z);

        // prints the complete map
        System.out.println("Updated TreeMap is : " + tmp);
    }
}
```

输出:

```
The initial TreeMap is : {one=1, two=3}
The previous value with two is : 3
Updated TreeMap is : {one=1, two=2}

```

**2。putAll() :** 它**将所有映射**从指定的映射复制到给定的映射，并在重复按键的情况下覆盖。

```
Parameters:
map : The mappings to be stored.
Return Value:
Not Available.
Exception:
NullPointerException : Thrown if specified map is null,
specified map contains a null key.

```

```
// Java code to demonstrate the working
// of putAll()
import java.io.*;
import java.util.*;
public class putAll {
    public static void main(String[] args)
    {

        // Declaring the tree maps of Integer and String
        TreeMap<String, Integer> tmp1 = new TreeMap<String, Integer>();
        TreeMap<String, Integer> tmp2 = new TreeMap<String, Integer>();

        // assigning the values in the tree map
        // using put()
        tmp1.put("two", 3);
        tmp1.put("one", 1);

        // assigning in 2nd TreeMap
        tmp2.put("three", 3);
        tmp2.put("two", 2);

        System.out.println("First treemap values are : " + tmp1);

        // use of putAll()
        // Putting 2nd map in 1st map
        tmp1.putAll(tmp2);

        System.out.println("Values after modifying 1st treemap : " + tmp1);
    }
}
```

输出:

```
First treemap values are : {one=1, two=3}
Values after modifying 1st treemap : {one=1, three=3, two=2}

```

**Exception**

**空指针异常:**如果**映射包含空键或在 putAll()中为空**，则会出现该异常。

```
// Java code to demonstrate the Exception
// of putAll()
import java.io.*;
import java.util.*;
public class putAll {
    public static void main(String[] args)
    {

        // Declaring the tree maps of Integer and String
        TreeMap<String, Integer> tmp1 = new TreeMap<String, Integer>();
        TreeMap<String, Integer> tmp2 = new TreeMap<String, Integer>();

        // assigning the values in the tree map
        // using put()
        tmp1.put("two", 3);
        tmp1.put("one", 1);

        // assigning in 2nd TreeMap
        tmp2.put("three", 3);
        tmp2.put(null, 2);

        System.out.println("First treemap values are : " + tmp1);

        // use of putAll()
        // Putting 2nd map in 1st map
        tmp1.putAll(tmp2);

        System.out.println("Values after modifying 1st treemap : " + tmp1);
    }
}
```

运行时错误:

```
Exception in thread "main" java.lang.NullPointerException
    at java.util.TreeMap.put(TreeMap.java:563)
    at putAll.main(putAll.java:21)

```

**实际应用:**这个功能可以存储数值，如果需要可以更新。这种功能主要在**目录和字典或记录**中有用。下面的一个小代码解释了如何组合数据库来获得游戏中的更新分数。

```
// Java code to demonstrate the Application
// of putAll()
import java.io.*;
import java.util.*;
public class putAllAppli {
    public static void main(String[] args)
    {

        // Declaring the tree maps of Integer and String
        TreeMap<String, Integer> Score1 = new TreeMap<String, Integer>();
        TreeMap<String, Integer> Score2 = new TreeMap<String, Integer>();

        // Assigning Scores at Drinks break
        Score1.put("Sachin", 40);
        Score1.put("Rahul", 32);
        Score1.put("Dhoni", 68);

        System.out.println("The scores till Drinks break are : " + Score1);

        // Assigning Scores at Lunch
        Score2.put("Rahul", 67);
        Score2.put("Dhoni", 102);
        Score2.put("Raina", 10);

        System.out.println("The scores at Lunch : " + Score2);

        // use of putAll()
        // Getting net score board
        Score1.putAll(Score2);

        System.out.println("Net scorecard is : " + Score1);
    }
}
```

输出:

```
The scores till Drinks break are : {Dhoni=68, Rahul=32, Sachin=40}
The scores at Lunch : {Dhoni=102, Rahul=67, Raina=10}
Net scorecard is : {Dhoni=102, Rahul=67, Raina=10, Sachin=40}

```

本文由 **[香巴拉维·辛格](https://www.facebook.com/shambhavi.singh.1217)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论