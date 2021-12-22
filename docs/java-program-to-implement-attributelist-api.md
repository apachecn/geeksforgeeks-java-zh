# 实现属性列表 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-attributelist-api/](https://www.geeksforgeeks.org/java-program-to-implement-attributelist-api/)

一个**属性列表**可以用来在一次调用中获取和设置多个 MBean 属性。这是一个只能包含属性的数组列表。属性列表必须在外部同步。

**申报:**

```java
public class AttributeList extends ArrayList
{
  // code
}
```

**属性列表应用编程接口的实现类:**

*   可序列化
*   可克隆的
*   可重复的
*   收藏品
*   目录
*   随机存取

**施工方:**

1.  **属性列表()–**构建一个新的空属性列表。
2.  **属性列表(属性列表)–**从另一个属性列表中构造一个新属性。
3.  **属性列表(int initial capacity)–**用指定的初始容量构建一个新的空属性列表。

**方法:**

1.  **添加(属性对象)–**方法将属性添加到列表中。
2.  **void add(int index，Attribute object)–**方法在列表中指定的索引处插入一个新的 Attribute。
3.  **布尔 addAll(属性列表)–**向列表追加属性的方法。
4.  **布尔 addAll(int index，AttributeList list)–**在指定索引处插入传递列表中所有属性的方法。
5.  **无效集(int 索引，Attribute 对象)–**在指定索引处更改属性的方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement AttributeList API

import java.util.Collection;
import java.util.List;
import javax.management.Attribute;
import javax.management.AttributeList;

public class AttributeListImpl {
    private AttributeList attributeList;

    // constructor for creating an empty AttributeList
    public AttributeListImpl()
    {
        attributeList = new AttributeList();
    }

    // constructor for creating an AttributeList containing
    // the elements of the AttributeList specified, in the
    // order in which they are returned by the
    // AttributeList's iterator.

    public AttributeListImpl(AttributeList list)
    {
        attributeList = new AttributeList();
    }

    // constructor for creating an AttributeList with the
    // specified initial capacity
    public AttributeListImpl(int initialCapacity)
    {
        attributeList = new AttributeList(initialCapacity);
    }

    // constructor for creating an AttributeList
    // containing the elements of the List
    // specified.

    public AttributeListImpl(List<Attribute> list)
    {
        attributeList = new AttributeList();
    }

    // this method appends an Attribute to the list
    public void add(Attribute object)
    {
        attributeList.add(object);
    }

    // this method inserts an attribute at a specified
    // position
    public void add(int index, Attribute object)
    {
        attributeList.add(index, object);
    }

    // this method inserts an specified element at
    // a specified position
    public void add(int index, Object element)
    {
        attributeList.add(index, element);
    }

    // this method appends a specified element to the list
    public boolean add(Object element)
    {
        return attributeList.add(element);
    }

    // this method appends all the elements of a
    // given list in the AttributeList.
    public boolean addAll(AttributeList list)
    {
        return attributeList.addAll(list);
    }

    // this method will appends all of the
    // elements of the given Collection
    // in the AttributeList.
    public boolean addAll(Collection<?> c)
    {
        return attributeList.addAll(c);
    }

    // Inserts all of the elements in the AttributeList
    // specified into this list, starting at the specified
    // position, in the order in which they are returned by
    // the Iterator of the AttributeList specified.
    public boolean addAll(int index, AttributeList list)
    {
        return attributeList.addAll(index, list);
    }

    // this method will add all of the elements of the
    // given collection at a the specified index
    public boolean addAll(int index, Collection<?> c)
    {
        return attributeList.addAll(index, c);
    }

    // this method Return a view of this list as a
    // List<Attribute>
    public List<Attribute> asList()
    {
        return attributeList.asList();
    }

    // this method will set the element at a given position
    public void set(int index, Attribute element)
    {
        attributeList.set(index, element);
    }

    // this method will replace the element at the specified
    // position in this list with the given element
    public Object set(int index, Object element)
    {
        return attributeList.set(index, element);
    }

    public static void main(String[] arg)
    {
        // creating object for AttributeListImpl object
        AttributeListImpl attributeList
            = new AttributeListImpl();

        attributeList.add(new Attribute("rose", 1));
        attributeList.add(new Attribute("sun-flower", 2));
        attributeList.add(new Attribute("tulip", 3));
        attributeList.add(new Attribute("orchid", 4));
        attributeList.add(new Attribute("marie-gold", 5));
        attributeList.add(new Attribute("hibiscus", 0));

        System.out.println(
            "The elements of the attributelist are");

        List<Attribute> flowerlist = attributeList.asList();

        int ind = 0;

        // iterating through the attribute List and
        // printing elements.
        while (ind < flowerlist.size()) {
            System.out.print(flowerlist.get(ind++) + " ");
        }

        System.out.println();

        // setting value = 6 at key = "hibiscus"
        attributeList.set(5, new Attribute("hibiscus", 6));

        System.out.println();
        System.out.println("after setting index 5");
        System.out.println(
            "the elements of the attributelist are");

        // iterating through the attribute List and
        // printing elements.
        flowerlist = attributeList.asList();

        ind = 0;
        while (ind < flowerlist.size()) {
            System.out.print(flowerlist.get(ind++) + " ");
        }
    }
}
```

**Output**

```java
The elements of the attributelist are
rose = 1 sun-flower = 2 tulip = 3 orchid = 4 marie-gold = 5 hibiscus = 0 

after setting index 5
the elements of the attributelist are
rose = 1 sun-flower = 2 tulip = 3 orchid = 4 marie-gold = 5 hibiscus = 6
```