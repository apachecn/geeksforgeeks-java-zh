# 如何在 Java 中将所有列表元素复制并添加到空数组列表中？

> 原文:[https://www . geesforgeks . org/如何将所有列表元素复制并添加到空的 java 数组列表中/](https://www.geeksforgeeks.org/how-to-copy-and-add-all-list-elements-to-an-empty-arraylist-in-java/)

我们可以使用 **addAll()方法**在数组列表中复制并添加列表项。此方法接受集合(例如。列表)作为参数，并在其调用 collection(例如。ArrayList)。此方法返回一个布尔值。如果集合成功添加，addAll()返回 true，否则返回 false。

**我们可以通过两种方式克隆列表:**

1.  使用 addAll()方法
2.  使用复制构造函数

**方法一:使用 addAll()方法**

**语法:**

> 公共布尔 addAll(集合 c)；

**参数:**它接受要克隆的集合作为其参数

**返回值:**这个方法返回一个布尔值。如果集合成功添加，addAll()返回 true，否则返回 false。

**异常:**如果指定的集合为空，将抛出空指针异常。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to clone the list

import java.util.ArrayList;
import java.util.List;

public class GFG {

    public static void main(String[] args)
    {
        // create ArrayList
        ArrayList<String> ArrList = new ArrayList<String>();

        // Adding elements to the ArrayList
        ArrList.add("item 1");
        ArrList.add("item 2");
        ArrList.add("item 3");

        System.out.println("ArrayList = " + ArrList);

        // create List
        List<String> ListItem = new ArrayList<String>();
        ListItem.add("item 4");
        ListItem.add("item 5");

        // add List items in ArrayList
        ArrList.addAll(ListItem);

        System.out.println(
            "After Adding List Item in ArrayList = "+ ArrList);
    }
}
```

**Output**

```java
ArrayList = [item 1, item 2, item 3]
After Adding List Item in ArrayList = [item 1, item 2, item 3, item 4, item 5]
```

**方法 2:使用复制构造器**

使用 Java 中的 ArrayList 构造函数，可以用另一个集合中的元素初始化一个新列表。

**语法:**

```java
ArrayList arrlist = new ArrayList(collection c);

```

这里，c 是包含要添加到该列表中的元素的集合。

**进场:**

1.  创建要克隆的列表。
2.  绕过原始列表克隆列表，作为数组列表的复制构造函数的参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to clone a List in Java 

import java.util.ArrayList; 
import java.util.Arrays; 
import java.util.List; 

class Example { 
    public static void main(String[] args) 
    { 
        // Create a list 
        List<String> original = Arrays.asList( 
                "GeeksForGeeks", 
                "Coding", 
                "Portal"); 

        // Clone the list 
        List<String> cloned_arraylist 
            = new ArrayList<String>(original); 

        System.out.println(cloned_arraylist); 
    } 
}
```

**Output**

```java
[GeeksForGeeks, Coding, Portal]
```