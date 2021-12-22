# 如何在 Java 中将 ArrayList 转换为 LinkedHashSet？

> 原文:[https://www . geesforgeks . org/how-convert-ArrayList-to-link edhashset-in-Java/](https://www.geeksforgeeks.org/how-to-convert-arraylist-to-linkedhashset-in-java/)

ArrayList 是一种数据结构，它克服了 Java 中常见数组的缺点，即必须事先明确指定数组的大小。数组数据结构的长度不能修改，由[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)数据结构处理。这种数据结构也被称为动态数组，可以根据需要增长或修改。它是 Collections 框架下的一个类，可以通过导入 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)包含在 java 程序中。

[LinkedHashSet](https://www.geeksforgeeks.org/arraylist-in-java/) 是 Java 中传统的 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类的增强版本，它提供了 HashSet 中缺少的额外的排序功能。它保持元素插入到其中的顺序，不像 HashSet 那样顺序是不可预测的。它是使用双链表实现的，可以使用迭代器进行迭代。

本文使用下面列出的 4 种不同的方法来处理数组列表到链接哈希表的转换:

1.  在初始化 LinkedHashSet 构造函数的过程中，将数组列表作为参数传递。
2.  使用 LinkedHashSet 类的 addAll()方法。
3.  在遍历数组列表的所有元素时，使用 LinkedHashSet 类的 add()方法。
4.  使用流首先将数组列表转换为集合，集合再转换为链接哈希集。

**接近 1**

使用这种方法，我们只需在初始化 LinkedHashSet 类时将 ArrayList 作为参数传递

**语法**

**LinkedHashSet(集合 C):** 用于用集合 C 的元素初始化 HashSet

> *linked hashset<E>hs = new linked hashset<E>(收藏 c)；*

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to convert ArrayList
// to LinkedHashSet

// importing the utils package
import java.util.*;

class GFG {

    // defining the method
    void arrayListToLinkedHashSet()
    {

        // initializing the ArrayList
        ArrayList<String> arrayList = new ArrayList<>();

        // adding values in the ArrayList
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // printing the list
        System.out.println("The array list : " + arrayList);

        // initializing the LinkedHashSet class
        // passing the ArrayList as parameter
        LinkedHashSet<String> linkedHashSet
            = new LinkedHashSet<String>(arrayList);

        // printing the LinkedHashSet
        System.out.println("The converted "
                           + "Linked Hash Set : "
                           + linkedHashSet);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling the method
        ob.arrayListToLinkedHashSet();
    }
}
```

**Output**

```
The array list : [Geeks, For, Geeks]
The converted Linked Hash Set : [Geeks, For]
```

**解释:**
数组列表包含三个条目，分别是【极客，对于，极客】。这将被转换为有序集，并且只包含两个值:**极客**和 **For。**既然[设置](https://www.geeksforgeeks.org/set-in-java/)不允许多个相似值。

**接近 2**

使用这种方法，我们在初始化 LinkedHashSet 类后使用它的预定义方法 **addAll()** 来填充 LinkedHashSet。

**语法:**

```
LinkedHashSet.addAll(Collection C)
```

**参数:**参数 *C* 是要添加到集合中的任何类型的集合。

**返回值:**如果该方法成功地将集合 *C* 的元素追加到该集合中，则该方法返回真，否则返回假。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to convert ArrayList
// to LinkedHashSet

// importing the java.utils package
import java.util.*;

class GFG {

    // defining the method
    void arrayListToLinkedHashSet()
    {

        // initializing the ArrayList
        ArrayList<String> arrayList = new ArrayList<>();

        // filling the ArrayList with values
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // printing the list
        System.out.println("The Array List : " + arrayList);

        // initializing the LinkedHashSet
        LinkedHashSet<String> linkedHashSet
            = new LinkedHashSet<>();

        // using the addAll() to
        // fill the HashSet
        linkedHashSet.addAll(arrayList);

        // printing the LinkedHashSet
        System.out.println("The Linked "
                           + "Hash Set : " + linkedHashSet);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling the method
        ob.arrayListToLinkedHashSet();
    }
}
```

**Output**

```
The Array List : [Geeks, For, Geeks]
The Linked Hash Set : [Geeks, For]
```

**接近 3**

使用这种方法，我们遍历数组列表，并在每次迭代中使用 LinkedHashSet 类的预定义 [add()](https://www.geeksforgeeks.org/linkedhashset-add-method-in-java-with-examples/) 方法用值填充 LinkedHashSet。

**语法:**

```
Hash_Set.add(Object element)
```

**参数:**参数*元素*的类型为 LinkedHashSet，是指要添加到集合中的元素。

**返回值:**如果该元素不在 LinkedHashSet 中，则函数返回 True 否则，如果该元素已经在 LinkedHashSet 中，则函数返回 False。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to convert ArrayList
// to LinkedHashSet

// importing the java.utils package
import java.util.*;

class GFG {

    // defining the method
    void arrayListToHashSet()
    {

        // initializing the ArrayList
        ArrayList<String> arrayList = new ArrayList<>();

        // filling the ArrayList with values
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // printing the list
        System.out.println("The Array List : " + arrayList);

        // declaring the iterator
        Iterator<String> itr = arrayList.iterator();

        // initializing the LinkedHashSet
        LinkedHashSet<String> linkedHashSet
            = new LinkedHashSet<>();

        // loop to iterate through the ArrayList
        while (itr.hasNext())

            // using the add()
            // to fill the HashSet
            linkedHashSet.add(itr.next());

        // printing the LinkedHashSet
        System.out.println("The Linked Hash Set : "
                           + linkedHashSet);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling the method
        ob.arrayListToHashSet();
    }
}
```

**Output**

```
The Array List : [Geeks, For, Geeks]
The Linked Hash Set : [Geeks, For]
```

**接近 4**

在这种方法下，我们首先将数组列表转换为流，然后将流转换为集合。这个集合最终被转换成一个链接的散列集合。[流](https://www.geeksforgeeks.org/stream-in-java/)类仅适用于 JDK 版本 8 或更高版本。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java program to convert ArrayList
// to LinkedHashSet

import java.util.*;
import java.util.stream.*;

class GFG {

    // defining the method
    void arrayListToLinkedHashSet()
    {

        // initializing the ArrayList
        ArrayList<String> arrayList = new ArrayList<>();

        // filling the ArrayList with values
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // printing the list
        System.out.println("The Array List : " + arrayList);

        // creating a stream from the ArrayList
        Stream<String> stream = arrayList.stream();

        // creating a set from the Stream
        // using the predefined toSet()
        // method of the Collectors class
        Set<String> set
            = stream.collect(Collectors.toSet());

        // converting the Set to
        // LinkedHashSet
        LinkedHashSet<String> linkedHashSet
            = new LinkedHashSet<>(set);

        // printing the LinkedHashSet
        System.out.println("The Linked Hash Set : "
                           + linkedHashSet);
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling the method
        ob.arrayListToLinkedHashSet();
    }
}
```

**Output**

```
The Array List : [Geeks, For, Geeks]
The Linked Hash Set : [Geeks, For]
```

**将自定义类对象的数组列表转换为链接哈希表**

以上示例说明了转换原始数据类型(如整数、字符串等)的数组列表的过程。在这里，我们将使用上述方法将自定义类对象的数组列表转换为 LinkedHashSet。转换的一个有趣特性是，这允许复制对象，而这在上述场景中是不允许的。同样的原因是，每次创建同一个类的新对象时，当比较对象时，用于在将元素输入集合之前检查元素的 equals()方法会找到唯一的引用，因为每个新对象都有一个新的引用。这允许相同的数据出现在 LinkedHashSet 的多个位置。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// java code to convert an ArrayList
// of custom class objects to
// LinkedHashSet

// importing the libraries
import java.util.*;

// the custom class
class Sports {

    // global variable name of type String
    // to hold the name of the sport
    private String name;

    // constructor
    public Sports(String name)
    {

        // initializing the name
        this.name = name;
    }

    // method to return the string
    public String returnString()
    {
        return name + " is a great sport";
    }
}

// primary class
class GFG {

    // declaring the method
    static void arrayListToLinkedHashSet()
    {

        // creating an array list of type
        // class Sports
        ArrayList<Sports> listOfSports
            = new ArrayList<Sports>();

        // adding the new instances of Sports
        // in the array list
        listOfSports.add(new Sports("Football"));
        listOfSports.add(new Sports("Basketball"));
        listOfSports.add(new Sports("Football"));

        // printing the list
        System.out.println("The Array List : "
                           + listOfSports);

        // declaring an iterator of type Sports
        // to iterate over the list
        Iterator<Sports> itr = listOfSports.iterator();

        // iterating over the list
        while (itr.hasNext())

            // printing the contents
            // by calling the returnString()
            System.out.println(itr.next().returnString());

        // initializing the linkedhashset
        // of type Sports
        LinkedHashSet<Sports> linkedHashSet
            = new LinkedHashSet<Sports>(listOfSports);

        // printing the contents of the
        // linked hash set
        System.out.println("The Linked Hash Set : "
                           + linkedHashSet);

        // declaring an iterator to iterate
        // over linkedhashset
        Iterator<Sports> itr1 = linkedHashSet.iterator();

        // iterating over the linkedhashset
        while (itr1.hasNext()) {

            // calling the returnString()
            // of Sports
            System.out.println(itr1.next().returnString());
        }
    }

    // Driver Code
    public static void main(String[] args)
    {

        // calling the method
        arrayListToLinkedHashSet();
    }
}
```

**Output**

```
The Array List : [Sports@4e50df2e, Sports@1d81eb93, Sports@7291c18f]
Football is a great sport
Basketball is a great sport
Football is a great sport
The Linked Hash Set : [Sports@4e50df2e, Sports@1d81eb93, Sports@7291c18f]
Football is a great sport
Basketball is a great sport
Football is a great sport
```

**说明:**
在第一行，打印了 ArrayList 的内容，可以看到是对 class Sports 的引用。在下面的三行中，打印了 Sports 类的 returnString()方法的内容。应该注意的是，所有引用都是唯一的，因此即使内容可能相同，LinkedHashSet 也允许它们。在下面一行中，打印了 LinkedHashSet 的内容，这些内容也是对体育课的引用。下面几行是 **returnString()** 方法调用。