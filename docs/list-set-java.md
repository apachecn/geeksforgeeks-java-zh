# Java 中要设置的列表

> 原文:[https://www.geeksforgeeks.org/list-set-java/](https://www.geeksforgeeks.org/list-set-java/)

给定一个列表([数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)或[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)，将其转换为 Java 中字符串的[集合](https://www.geeksforgeeks.org/set-in-java/) ( [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 或 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) )。

**方法 1(简单)**
我们简单地创建一个列表。我们遍历给定的集合，一个接一个地向列表中添加元素。

```
// Java program to demonstrate conversion of
// list to set using simple traversal
import java.util.*;

class Test {
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> aList = Arrays.asList("Geeks", "for",
                     "GeeksQuiz", "GeeksforGeeks", "GFG");

        Set<String> hSet = new HashSet<String>();
        for (String x : aList)
            hSet.add(x);

        System.out.println("Created HashSet is");
        for (String x : hSet)
            System.out.println(x);

        // We can created TreeSet same way
    }
}
```

**方法 2(使用 HashSet 或 TreeSet 构造函数)**

```
// Java program to demonstrate conversion of
// list to set using constructor
import java.util.*;

class Test {
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> aList = Arrays.asList("Geeks", "for",
                     "GeeksQuiz", "GeeksforGeeks", "GFG");

        // Creating a hash set using constructor
        Set<String> hSet = new HashSet<String>(aList);

        System.out.println("Created HashSet is");
        for (String x : hSet)
            System.out.println(x);

        System.out.println("Created TreeSet is");
        Set<String> tSet = new TreeSet<String>(aList);
        System.out.println("Created TreeSet is");
        for (String x : tSet)
            System.out.println(x);
    }
}
```

**方法 3(使用 addAll 方法)**

```
// Java program to demonstrate conversion of
// Set to array using addAll() method.
import java.util.*;

class Test {
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> aList = Arrays.asList("Geeks", "for",
                    "GeeksQuiz", "GeeksforGeeks", "GFG");

        Set<String> hSet = new HashSet<String>(aList);
        hSet.addAll(aList);
        System.out.println("Created HashSet is");
        for (String x : hSet)
            System.out.println(x);

        Set<String> tSet = new TreeSet<String>(aList);
        tSet.addAll(aList);
        System.out.println("Created TreeSet is");
        for (String x : tSet)
            System.out.println(x);
    }
}
```

**方法 4(使用 Java 中的[流](https://www.geeksforgeeks.org/stream-in-java/) )**
我们使用 Java 中的[流](https://www.geeksforgeeks.org/stream-in-java/)将给定列表转换为流，然后流进行设置。这仅适用于 Java 8 或之后的版本。

```
// Java program to demonstrate conversion of
// Set to list using stream
import java.util.*;
import java.util.stream.*;

class Test {
    public static void main(String[] args)
    {

        // Creating a list of strings
        List<String> aList = Arrays.asList("Geeks", "for",
                    "GeeksQuiz", "GeeksforGeeks", "GFG");

        // Converting to set using stream
        Set<String> set = aList.stream().collect(Collectors.toSet());

        for (String x : set)
            System.out.println(x);
    }
}
```