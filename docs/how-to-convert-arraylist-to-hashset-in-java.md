# 如何在 Java 中将 ArrayList 转换成 HashSet？

> 原文:[https://www . geesforgeks . org/how-convert-ArrayList-to-hashset-in-Java/](https://www.geeksforgeeks.org/how-to-convert-arraylist-to-hashset-in-java/)

[](https://www.geeksforgeeks.org/arraylist-in-java/)****:**在 Java 中，数组列表可以有重复项，也可以保持插入顺序。**

**[**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/)**:**HashSet 是 Set 的实现类。它不允许重复，并在内部使用哈希表。**

****数组列表转换为 HashSet 有四种方式:****

1.  **使用构造函数。**
2.  **通过迭代每个元素并将其添加到 HashSet 中来使用 add()方法。**
3.  **使用 addAll()方法，将所有元素一次性添加到 HashSet 中。**
4.  **使用流**

****方法一:使用构造器****

**在这个例子中，我们将创建一个数组列表对象，并将其传递给 HashSet 的构造函数。转换成 HashSet 是最简单的方法。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to convert ArrayList
// to HashSet using constructor

import java.util.HashSet;
import java.util.ArrayList;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // adding elements to ArrayList object
        ArrayList<String> gfg = new ArrayList<>();

        gfg.add("data structure");
        gfg.add("competitive programming");
        gfg.add("Interviews");
        gfg.add("FANG");
        gfg.add("FANG");

        // pass ArrayList object into the HashSet object
        // constructor
        HashSet<String> hashSet = new HashSet<>(gfg);

        // printing every element in Set

        for (String value : hashSet) {
            System.out.println(value);
        }
    }
}
```

****Output**

```
FANG
data structure
Interviews
competitive programming
```** 

****方法二:使用 add()方法:****

**在本文中，我们将迭代数组列表并添加 HashSet 中的每个元素。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to convert ArrayList
// to HashSet using add() method

import java.io.*;
import java.util.ArrayList;
import java.util.HashSet;
class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> gfg = new ArrayList<>();

        // adding element to ArrayList
        gfg.add("data structure");
        gfg.add("competitive programming");
        gfg.add("Interviews");
        gfg.add("FANG");
        gfg.add("FANG");

          // adding each Arraylist element inside the HashSet
        HashSet<String> hashSet = new HashSet<>();

        // printing each element
        gfg.forEach(value -> { hashSet.add(value); });

        for (String value : hashSet) {
            System.out.println(value);
        }
    }
}
```

****Output**

```
FANG
data structure
Interviews
competitive programming
```** 

****方法三:使用** [**addAll()**](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/) **方法****

**在这个例子中，我们将简单地在 HashSet 中使用 addALL()方法添加完整的 ArrayList 对象。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to convert ArrayList
// to HashSet using addAll() method

import java.io.*;
import java.util.ArrayList;
import java.util.HashSet;
class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> gfg = new ArrayList<>();

        // adding element into ArrayList object
        gfg.add("data structure");
        gfg.add("competitive programming");
        gfg.add("Interviews");
        gfg.add("FANG");
        gfg.add("FANG");

        // adding ArrayList to hashset using addAll() method
        HashSet<String> hashSet = new HashSet<>();
        hashSet.addAll(gfg);

        // printing each element of hashset
        for (String value : hashSet) {
            System.out.println(value);
        }
    }
}
```

****Output**

```
FANG
data structure
competitve programming
Interviews
```** 

****方法四:使用** [**溪流**](https://www.geeksforgeeks.org/stream-in-java/) **。****

**在这种方法中，我们将使用流来迭代每个数组列表元素，然后使用 collect 方法将每个项目添加到一个集合中。流是 java 8 的一部分**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to convert ArrayList
// to HashSet using streams

import java.io.*;
import java.util.ArrayList;
import java.util.Set;
import java.util.HashSet;
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> gfg = new ArrayList<>();
        gfg.add("data structure");
        gfg.add("competitive programming");
        gfg.add("Interviews");
        gfg.add("FANG");
        gfg.add("FANG");

        // using stream to convert the ArrayList into set
        // then typecast into HashSet<String>
        HashSet<String> hashSet
            = (HashSet<String>)gfg.stream().collect(
                Collectors.toSet());

        // printing values of the hashSet
        for (String value : hashSet) {
            System.out.println(value);
        }
    }
}
```

****Output**

```
FANG
data structure
Interviews
competitive programming
```**