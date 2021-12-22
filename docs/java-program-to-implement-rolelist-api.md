# 实现角色列表 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-角色列表-api/](https://www.geeksforgeeks.org/java-program-to-implement-rolelist-api/)

角色列表代表角色列表(角色对象)。当创建一个关系时，当试图在一个关系中设置多个角色时，或者通过 *setRoles()* 方法，它被用作一个参数。它作为角色结果的一部分返回，以使角色成功获得角色。

> *   [爪哇。朗。对象](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html)
> 
> [Java . util . abstract collection](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractCollection.html)
> 
> *   [爪哇。乌提尔。摘要列表](https://docs.oracle.com/javase/7/docs/api/java/util/AbstractList.html)T2【E】T3
> *   T14】爪哇 .有用。数组列表

**语法:**

```java
public class RoleList extends ArrayList<Object> ;
```

**构建角色列表的方法**

1.  ***角色列表()*** :构建一个空的角色列表。
2.  ***角色列表(int initial_capacity)*** :用指定的初始能力构建一个空的角色列表。
3.  ***角色列表(列表<角色>列表)*** :按照列表迭代器返回的顺序，构建包含指定列表元素的角色列表。

**实现:**所有可实现的接口如下:

1.  [可序列化](https://docs.oracle.com/javase/7/docs/api/java/io/Serializable.html)
2.  [可克隆](https://docs.oracle.com/javase/7/docs/api/java/lang/Cloneable.html)
3.  [可重复](https://docs.oracle.com/javase/7/docs/api/java/lang/Iterable.html) < [物体](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html) >
4.  [集合](https://docs.oracle.com/javase/7/docs/api/java/util/Collection.html) < [对象](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html) >
5.  [列表](https://docs.oracle.com/javase/7/docs/api/java/util/List.html) < [对象](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html) >
6.  随机

实现角色列表应用编程接口的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement RoleList API

// Importing libraries
import java.util.Collection;
import java.util.LinkedList;
import java.util.List;
import javax.management.MalformedObjectNameException;
import javax.management.ObjectName;
import javax.management.relation.Role;
import javax.management.relation.RoleList;

public class GFG {

    private RoleList rList;

    // Create an empty RoleList
    public GFG() { rList = new RoleList(); }

    // Create an empty RoleList
    // with the initial capacity
    public GFG(int inicapacity)
    {
        rList = new RoleList(inicapacity);
    }

    // Create a RoleList containing the elements of the List
    // specified in order in which they are returned by the
    // List's iterator
    public GFG(List<Role> list)
    {
        rList = new RoleList(list);
    }

    // Inserts element at the specified position in list
    public void add(int index, Object element)
    {
        rList.add(index, element);
    }

    // Inserts the role specified at the position
    //  specified as an element
    public void add(int index, Role role)
    {
        rList.add(index, role);
    }

    // Appends the specified element to the end of List
    public boolean add(Object o) 
    {
      return rList.add(o); 
    }

    // Adds the Role specified as the last element
    public void add(Role role) 
    { 
      rList.add(role); 
    }

    // Appends all elements in the specified collections
    // to the end of list, in the order that
    // they are returned by the specified collection's
    // Iterator
    public boolean addAll(Collection<?> c)
    {
        return rList.addAll(c);
    }

    // Inserts all elements in the specified collection into
    // list starting from the specified position.
    public boolean addAll(int index, Collection<?> c)
    {
        return rList.addAll(index, c);
    }

    // Inserts all elements in the RoleList specified into
    // list, starting from the specified position,in the
    // order in which they are returned by the Iterator
    public boolean addAll(int index, RoleList roleList)
    {
        return this.rList.addAll(index, rList);
    }

    // Append all elements in the RoleList specified to the
    // end, in the order in which they are returned.
    public boolean addAll(RoleList rList)
    {
        return rList.addAll(rList);
    }

    // Return a view of list as a List<Role>
    public List<Role> asList() 
    { 
      return rList.asList(); 
    }

    // Replace the element at the specified position in list
    // with the specified element
    public Object set(int index, Object element)
    {
        return rList.set(index, element);
    }

    // Set the element at the position specified
    // to be the role specified
    public void set(int index, Role role)
    {
        rList.set(index, role);
    }

    // Main driver method
    public static void main(String[] arg)
        throws MalformedObjectNameException
    {
        GFG rList = new GFG();
        List<ObjectName> rlist1
            = new LinkedList<ObjectName>();
        rlist1.add(
            new ObjectName("domain1_", "key1_", "value1_"));
        rlist1.add(
            new ObjectName("domain2_", "key2_", "value3_"));
        rList.add(0, new Role("1_rolename", rlist1));

        List<ObjectName> rList2
            = new LinkedList<ObjectName>();
        rList2.add(
            new ObjectName("domain3_", "key3_", "value3_"));
        rList2.add(
            new ObjectName("domain4_", "key4_", "value4_"));
        rList.add(1, new Role("2_rolename", rList2));

        List<Role> list = rList.asList();
        int index = 0;
        while (index < list.size()) {
            System.out.println(list.get(index++) + " ");
        }
        System.out.println();
    }
}
```

**Output**

```java
role name: 1_rolename; role value: domain1_:key1_=value1_, domain2_:key2_=value3_ 
role name: 2_rolename; role value: domain3_:key3_=value3_, domain4_:key4_=value4_
```