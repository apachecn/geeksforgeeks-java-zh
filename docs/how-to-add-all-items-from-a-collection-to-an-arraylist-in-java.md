# 如何用 Java 将集合中的所有项添加到数组列表中？

> 原文:[https://www . geesforgeks . org/如何将集合中的所有项目添加到 java 中的数组列表/](https://www.geeksforgeeks.org/how-to-add-all-items-from-a-collection-to-an-arraylist-in-java/)

给定一个带有一些值的[集合](https://www.geeksforgeeks.org/collections-in-java-2/)，任务是将该集合的所有项目添加到 Java 中的[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中。

**插图:**

```
Input: Collection = [1, 2, 3] 
Output: ArrayList = [1, 2, 3]
```

```
Input: Collection = [GFG, Geek, GeeksForGeeks] 
Output: ArrayList = [GFG, Geek, GeeksForGeeks] 
```

**进场:**

1.  获取要将其项添加到数组列表中的集合
2.  [创建数组列表](https://www.geeksforgeeks.org/initialize-an-arraylist-in-java/)
3.  使用 [ArrayList.addAll()方法](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/)将集合的所有项目添加到该 ArrayList 中
4.  已创建包含所有集合项的数组列表。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Add All Items from a collection
// to an ArrayList

// Importing required classes
import java.io.*;
import java.util.*;
import java.util.stream.*;

// Main class
class GFG {

    // Method 1
    // To add all items from a collection
    // to an ArrayList
    public static <T> ArrayList<T>
    createArrayList(List<T> collection)
    {

        // Creating an ArrayList
        ArrayList<T> list = new ArrayList<T>();

        // Adding all the items of Collection
        // into this ArrayList
        list.addAll(collection);

        return list;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Getting array elements as list
        // and storing in a List object
        List<Integer> collection1 = Arrays.asList(1, 2, 3);

        // Printing elements in above List object
        System.out.println("ArrayList with all "
                           + "elements of collection "
                           + collection1 + ": "
                           + createArrayList(collection1));

        // Again creating another List class object
        List<String> collection2 = Arrays.asList(
            "GFG", "Geeks", "GeeksForGeeks");

        // Printing elements in above List object
        System.out.println("ArrayList with all"
                           + " elements of collection "
                           + collection2 + ": "
                           + createArrayList(collection2));
    }
}
```

**Output**

```
ArrayList with all elements of collection [1, 2, 3]: [1, 2, 3]
ArrayList with all elements of collection [GFG, Geeks, GeeksForGeeks]: [GFG, Geeks, GeeksForGeeks]
```