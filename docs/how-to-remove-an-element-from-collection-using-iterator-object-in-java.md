# 如何在 Java 中使用迭代器对象从集合中移除元素？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的对象迭代器从集合中移除元素/](https://www.geeksforgeeks.org/how-to-remove-an-element-from-collection-using-iterator-object-in-java/)

Java 中的 [**【集合】**](https://www.geeksforgeeks.org/collections-in-java-2/) 是一组像 List、set、Queue 这样的接口。Java 中的 [**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/) 用于迭代或遍历集合的元素。Java 中迭代器有三种类型，分别是**枚举器**、**迭代器**、**T13】和**列表迭代器。****

**使用迭代器从集合中移除元素的两种方法:**

1.  使用迭代器
2.  使用列表迭代器

**方法 1:使用迭代器**

*   创建一个列表，并使用 add()方法将元素添加到列表中。
*   Iterator 对象用于使用 **hasNext()** 和 **next()** 方法迭代列表的元素。
*   如果在 while 循环中使用该条件，并且满足该条件，则使用 **remove()** 方法移除特定元素。
*   当整个列表被再次遍历时，被移除的元素不再出现在列表中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Remove an Element from 
// Collection using Iterator 

import java.util.ArrayList;
import java.util.Iterator;
class IteratorDemo 
{
    public static void main(String[] args) 
    {
        ArrayList<Integer> l = new ArrayList<Integer>();

        for(int i=0;i<=50;i=i+5)
        {
            l.add(i);
        }

        Iterator<Integer> itr = l.iterator();

        System.out.println("List before removal");

        for(int i=0;i<l.size();i++)
        {
            System.out.print(l.get(i)+" ");
        }

        while(itr.hasNext())
        {
            if(itr.next()%2==1)
                itr.remove();
        }

        System.out.println("\nList after removal");

        for(int i=0;i<l.size();i++)
        {
            System.out.print(l.get(i)+" ");
        }
    }

}
```

**Output**

```
List before removal
0 5 10 15 20 25 30 35 40 45 50 
List after removal
0 10 20 30 40 50
```

**方法 2:使用列表迭代器**

*   创建一个列表，并使用 add()方法将元素添加到列表中。
*   ListIterator 对象用于使用 hasNext()和 Next()方法迭代列表的元素。
*   while 循环中使用 if 条件，当条件满足时，使用 remove()方法移除特定元素。
*   当整个列表被再次遍历时，被移除的元素不再出现在列表中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Remove an Element from
// Collection using ListIterator

import java.util.ArrayList;
import java.util.ListIterator;

public class ListIteratorDemo {
    public static void main(String[] args)
    {
        ArrayList<String> l = new ArrayList<String>();

        l.add("January");
        l.add("February");
        l.add("March");
        l.add("April");
        l.add("May");
        l.add("June");
        l.add("July");
        l.add("August");

        ListIterator<String> itr = l.listIterator();

        System.out.println("List before removal");

        for (int i = 0; i < l.size(); i++)
            System.out.print(l.get(i) + " ");

        while (itr.hasNext()) {
            if (itr.next().equals("March")) {
                itr.remove();
            }
        }

        System.out.println("\nList after removal");

        for (int i = 0; i < l.size(); i++)
            System.out.print(l.get(i) + " ");
    }
}
```

**Output**

```
List before removal
January February March April May June July August 
List after removal
January February April May June July August
```