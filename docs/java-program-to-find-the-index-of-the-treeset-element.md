# 查找树集合元素索引的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-the-index-of-the-treeset-element/](https://www.geeksforgeeks.org/java-program-to-find-the-index-of-the-treeset-element/)

与像[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)或[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)这样的列表类不同，[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)类不允许使用索引访问元素。没有使用索引访问 TreeSet 元素的直接方法，因此找到元素的索引并不简单。

**方法:**主要有以下三种标准方法:

1.  通过将[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)转换为[列表](https://www.geeksforgeeks.org/arraylist-in-java/)
2.  使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)
3.  使用 TreeSet 类的 [*耳机()*](https://www.geeksforgeeks.org/treeset-headset-method-in-java/) 方法

**方法 1:** 通过将[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)转换为[列表](https://www.geeksforgeeks.org/arraylist-in-java/)

像 ArrayList 或 LinkedList 这样的 List 类提供了 [*indexOf()*](https://www.geeksforgeeks.org/list-indexof-method-in-java-with-examples/) 方法来查找元素索引。我们可以将 TreeSet 转换为 ArrayList，然后使用[*indexOf()*](https://www.geeksforgeeks.org/list-indexof-method-in-java-with-examples/)*方法。此方法返回此列表中指定元素的第一个匹配项的索引，如果此列表不包含该元素，则返回-1。*

***语法:***

```java
*public int indexOf(Object o) ;*
```

***参数:**该函数只有一个参数，即列表中要搜索的元素。*

***返回:**此方法返回列表中给定元素第一次出现的索引，如果该元素不在列表中，则返回“-1”。*

***例***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java Program to find the index of TreeSet element
// using List by converting TreeSet to a List

// Importing ArrayList, List and TreeSet classes
// from java.util package
import java.util.ArrayList;
import java.util.List;
import java.util.TreeSet;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a object of the TreeSet class
        // Declaring object of Integer type
        TreeSet<Integer> treeSet = new TreeSet<Integer>();

        // Adding the element to the TreeSet
        // Custom inputs
        treeSet.add(34);
        treeSet.add(23);
        treeSet.add(43);
        treeSet.add(41);
        treeSet.add(35);
        treeSet.add(33);

        // Printing all the elements in the TreeSet object
        System.out.println("TreeSet contains: " + treeSet);

        // Printing indexes of elements using indexOf()
        // method Index of element number 1
        System.out.println("Index of 23: "
                           + indexOf(treeSet, 23));

        // Index of element number 2
        System.out.println("Index of 43: "
                           + indexOf(treeSet, 43));

        // Index of element number 3
        System.out.println("Index of 35: "
                           + indexOf(treeSet, 35));

        // Index of element number 4
        System.out.println("Index of 55: "
                           + indexOf(treeSet, 55));
    }

    // Method - indexOf()
    private static int indexOf(TreeSet<Integer> set,
                               Integer element)
    {

        // Step 1: Convert TreeSet to ArrayList or
        // LinkedList
        List<Integer> list = new ArrayList<Integer>(set);

        // Step 2: Use the indexOf method of the List
        return list.indexOf(element);
    }
}*
```

***Output**

```java
TreeSet contains: [23, 33, 34, 35, 41, 43]
Index of 23: 0
Index of 43: 5
Index of 35: 3
Index of 55: -1
```* 

***方法 2:** 使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)*

***程序:***

1.  *使用迭代器方法对 TreeSet 元素进行迭代器。*
2.  *一旦获取了迭代器，迭代元素并根据要求从**用户或自定义输入中搜索指定的元素，如下所示，以便理解。***

*****例*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Java Program to find the index of the element
// in the TreeSet using Iterator
// Using an Iterator

// Importing Iterator and TreeSet class from
// java.util package
import java.util.Iterator;
import java.util.TreeSet;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of TreeSet class
        // Declaring object of Integer type
        TreeSet<Integer> treeSet = new TreeSet<Integer>();

        // Adding the elements to the TreeSet
        // Custom inputs
        treeSet.add(34);
        treeSet.add(23);
        treeSet.add(43);
        treeSet.add(41);
        treeSet.add(35);
        treeSet.add(33);

        // Printing the element in the TreeSet
        System.out.println("TreeSet contains: " + treeSet);

        // Printing the indexes of elements in above TreeSet
        // object
        System.out.println("Index of 23: "
                           + indexOf(treeSet, 23));
        System.out.println("Index of 43: "
                           + indexOf(treeSet, 43));
        System.out.println("Index of 35: "
                           + indexOf(treeSet, 35));
        System.out.println("Index of 55: "
                           + indexOf(treeSet, 55));
    }

    // Method - indexOf()
    private static int indexOf(TreeSet<Integer> set,
                               Integer element)
    {

        int index = -1;

        // Get an iterator
        Iterator<Integer> itr = set.iterator();

        Integer currentElement = null;
        int currentIndex = 0;

        // Condition check using hasNext() method which
        // holds true till single element in List is
        // remaining
        while (itr.hasNext()) {

            currentElement = itr.next();

            // Checking if the current element equals
            // the element whose index is tried to search
            if (currentElement.equals(element)) {

                // Return the index of the element
                return currentIndex;
            }

            // Increment the index number
            currentIndex++;
        }

        // Return the index -1
        // if the element do not exists
        return index;
    }
}***
```

*****Output**

```java
TreeSet contains: [23, 33, 34, 35, 41, 43]
Index of 23: 0
Index of 43: 5
Index of 35: 3
Index of 55: -1
```*** 

*****方法:3** 使用 TreeSet 类的 [*耳机()*](https://www.geeksforgeeks.org/treeset-headset-method-in-java/) 方法***

***TreeSet 类的[*【headSet()*](https://www.geeksforgeeks.org/treeset-headset-method-in-java/)方法返回元素少于指定元素的部分 TreeSet 的视图。由于 TreeSet 的元素会按照元素的自然顺序或通过自定义比较器自动排序，因此耳机大小将等于比指定元素小或小的元素数量。如果我们将 TreeSet 元素放在一个列表中，那么这个数字将等于元素的索引。***

***插图:***

> ***如果 TreeSet 包含[1，2，3，4]，那么元素 3 的头戴式耳机将包含元素[1，2]。耳机的大小将是 2，这将是元素 3 的索引。因此，如果我们得到耳机的大小，那么它将等于我们必须找到索引的元素的位置。***

*****例*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
***// Java Program to find the index of element
// in TreeSet using HeadSet
// Using the headSet() method of the TreeSet class

// Importing TreeSet class from
// java.util package
import java.util.TreeSet;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Making the new object of TreeSet class
        TreeSet<Integer> treeSet = new TreeSet<Integer>();

        // Adding the elements to the TreeSet
        treeSet.add(34);
        treeSet.add(23);
        treeSet.add(43);
        treeSet.add(41);
        treeSet.add(35);
        treeSet.add(33);

        // Printing the elements of the TreeSet
        System.out.println("TreeSet contains: " + treeSet);

        // Printing the indexes of elements
        // in above TreeSet object
        System.out.println("Index of 23: "
                           + indexOf(treeSet, 23));
        System.out.println("Index of 43: "
                           + indexOf(treeSet, 43));
        System.out.println("Index of 35: "
                           + indexOf(treeSet, 35));
        System.out.println("Index of 55: "
                           + indexOf(treeSet, 55));
    }

    // Method - indexOf() method
    private static int indexOf(TreeSet<Integer> set,
                               Integer element)
    {

        int index = -1;

        // If the element exists in the TreeSet
        if (set.contains(element)) {

            // The element index will be equal to the
            // size of the headSet for the element
            index = set.headSet(element).size();
        }

        // Return the index of the element
        // Value will be -1 if the element
        // do not exist in the TreeSet
        return index;
    }
}***
```

*****Output**

```java
TreeSet contains: [23, 33, 34, 35, 41, 43]
Index of 23: 0
Index of 43: 5
Index of 35: 3
Index of 55: -1
```***