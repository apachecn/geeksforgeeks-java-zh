# 如何在 Java 中迭代 HashSet？

> 原文:[https://www . geesforgeks . org/how-iterate-hashset-in-Java/](https://www.geeksforgeeks.org/how-to-iterate-hashset-in-java/)

[**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 扩展 [抽象设置](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/) 并实现设置界面。它创建一个集合，该集合使用一个散列表进行存储。它通过一种叫做散列的机制来存储信息。在哈希中，密钥的信息内容用于确定一个唯一的值，称为其哈希代码。

有三种简单的方法可以迭代 HashSet，如下所示:

1.  使用迭代器
2.  不使用迭代器(用于循环)
3.  使用 for-each 循环

**方法 1:** [迭代器](https://www.geeksforgeeks.org/iterators-in-java/)方法

在这个方法中，我们借助迭代器迭代 HashSet。首先，我们借助 Java 中的**迭代器()**方法，制作一个迭代器来迭代 HashSet。

```
// Create a iterator of integer type to iterate HashSet

Iterator<Integer> it = set.iterator();
```

然后借助 Java 中的 **hasNext()** 和 **Next()** 方法迭代 HashSet。其中**hashnext()**方法检查 HashSet 是否有元素， **Next()** 方法访问 HashSet 的数据。

**注意:**在 hasNext()之后只使用 Next()方法一次。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate the HashSet
// using iterator

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a new HashSet for iteration
        HashSet<Integer> set = new HashSet<>();

        // Add data to HashMap
        set.add(10);
        set.add(20);

        // Duplicates not allowed in HashMap, so avoid by
        // HashMap
        set.add(10);
        set.add(50);

        // Duplicates not allowed in HashMap, so avoid by
        // HashMap
        set.add(50);

        // Create a iterator of type integer to iterate
        // HashSet
        Iterator<Integer> it = set.iterator();

        System.out.println(
            "Iterate HashSet using iterator : ");

        // Iterate HashSet with the help of hasNext() and
        // next() method
        while (it.hasNext()) {

            // Print HashSet values
            System.out.print(it.next() + " ");
        }
    }
}
```

**Output**

```
Iterate HashSet using iterator : 
50 20 10
```

**方法 2:** 使用 for 循环迭代

在这个方法中，我们使用一个简单的**循环**来迭代 HashSet。下面是这种方法的实现:

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate the HashSet
// using for loop

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a new HashSet for iteration
        HashSet<String> set = new HashSet<>();

        // Add data to HashSet
        set.add("Hello");
        set.add("geeks");
        set.add("on");

        //  duplicates not allowed in HashMap, so avoid by
        //  HashMap
        set.add("geeks");
        set.add("for");

        //  duplicates not allowed in HashMap, so avoid by
        //  HashMap
        set.add("geeks");

        System.out.println(
            "Iterate HashSet using for loop : ");

        // Iterate throw a simple for loop
        for (String ele : set) {
            // Print HashSet data
            System.out.print(ele + " ");
        }
    }
}
```

**Output**

```
Iterate HashSet using for loop : 
Hello geeks for on
```

**方法三:使用 forEach()方法**

在这个方法中，我们使用 Java 中的 **forEach()** 循环迭代 HashSet。下面是这种方法的实现:

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate using forEach() loop

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a new HashSet for iteration
        HashSet<String> set = new HashSet<>();

        // Add data to HashSet
        set.add("Hello");
        set.add("geeks");
        set.add("on");

        //  duplicates not allowed in HashMap, so avoid by
        //  HashMap
        set.add("geeks");
        set.add("for");

        //  duplicates not allowed in HashMap, so avoid by
        //  HashMap
        set.add("geeks");

        System.out.println(
            "Iterate HashSet using forEach loop : ");

        // Iterate throw a forEach method in Java
        set.forEach(System.out::println);
    }
}
```

**Output**

```
Iterate HashSet using forEach loop : 
Hello
geeks
for
on
```