# 在 Java 中实现 roleundsolvedlist API

> 原文:[https://www . geesforgeks . org/impering-rolenresolvedlist-API-in-Java/](https://www.geeksforgeeks.org/implementing-roleunresolvedlist-api-in-java/)

应用编程接口是应用程序编程接口的缩写，它是允许两个应用程序相互通信的软件。[角色未解析列表](https://www.geeksforgeeks.org/java-program-to-implement-rolelist-api/)代表角色未解析对象的列表，角色未解析对象代表由于试图访问、读取或写入角色时遇到一些问题而未从关系中检索到的角色。因此，角色解算列表应用编程接口是一个与内部文件通信以检索对象含义的程序，代表由于某些问题**而不能从关系中检索的角色。**

**先决条件:**

**(A) Packages:** 在 java 的 RoleUnresolvedList API 程序中，为了检索程序中使用的对象的含义和用途，使用了各种 Packages。下图显示了程序中导入的包:

```java
import java.util.Collection;
import java.util.LinkedList;
import java.util.List;
import javax.management.MalformedObjectNameException;
import javax.management.ObjectName;
import javax.management.relation.RoleUnresolved;
import javax.management.relation.RoleUnresolvedList;
```

> **注:**为了进一步了解，请仔细阅读以下软件包。

**(二)施工方使用的**

*   **roleundresolvedlist():**用于构造空的 roleundresolvedlist。
*   **角色未解决列表(int initialCapacity):** 用于构建指定了初始容量的空角色未解决列表。
*   **角色未解决列表(列表<角色未解决列表>)**:用于构建包含指定列表元素的角色未解决列表。它是按照列表迭代器返回的顺序构造的。

**(C)方法**

*   [***add(int index，Object element)***](https://www.geeksforgeeks.org/list-addint-index-e-element-method-in-java/)*:*此方法用于将特定元素插入特定位置。
*   [***add(int index，role Unresolved role)***](https://www.geeksforgeeks.org/java-program-to-implement-rolelist-api/)*:*此方法在指定位置插入指定为元素的 Unresolved role。
*   **添加(Object o)** :在列表末尾追加指定元素。
*   ***添加(角色未解析角色)** :* 将添加列表最后一个元素指定的角色未解析。
*   [***addAll(收藏<？> c)***](https://www.geeksforgeeks.org/vector-addall-method-in-java/) *:* 它会在末尾追加指定列表中的元素。
*   [***addAll(int index，Collection <？>c)***](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/)***:***它会在指定位置插入元素。
*   ***addAll(int index，roleundsolvedlist roleList):***从指定位置开始，按照指定 roleundsolvedlist 的迭代器返回的顺序，将指定 roleundsolvedlist 中的所有元素插入此列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement RoleUnresolvedList API

// Packages are imported whose methods
// will be used withinProgram
// Importing classes drom java.util package
import java.util.Collection;
import java.util.LinkedList;
import java.util.List;
// Importing javax.management package
import javax.management.MalformedObjectNameException;
import javax.management.ObjectName;
import javax.management.relation.RoleUnresolved;
import javax.management.relation.RoleUnresolvedList;

// Class
public class GFG

{
    private RoleUnresolvedList roleUnresolvedList;

    // Constructor 1
    // It Constructs an empty RoleUnresolvedList
    public GFG()
    {
        roleUnresolvedList = new RoleUnresolvedList();
    }

    // Constructor 2
    // Constructs an empty RoleUnresolvedList
    // with the initial capacity specified
    public GFG(int initialCapacity)

    {
        roleUnresolvedList
            = new RoleUnresolvedList(initialCapacity);
    }

    // Constructor 3
    // It Constructs a RoleUnresolvedList containing
    // the elements of the List specified
    public GFG(List<RoleUnresolved> list)

    {
        roleUnresolvedList = new RoleUnresolvedList(list);
    }

    // Method 1
    // Inserts the specified element at the specified
    // position in this list
    public void add(int index, Object element)

    {
        roleUnresolvedList.add(index, element);
    }

    // Method 2
    // Inserts the unresolved role specified as an element
    // at the position specified.
    public void add(int index, RoleUnresolved role)
    {
        roleUnresolvedList.add(index, role);
    }

    // Method 3
    // Appends the specified element to the end of this list
    public boolean add(Object o)
    {
        return roleUnresolvedList.add(o);
    }

    // Method 4
    // Adds the RoleUnresolved specified as the last element
    // of the list
    public void add(RoleUnresolved role)
    {
        roleUnresolvedList.add(role);
    }

    // Method 5
    // Appends all of the elements in the specified
    // collection to the end of list, in the order that they
    // are returned by the specified collection's Iterator.
    public boolean addAll(Collection<?> c)
    {
        return roleUnresolvedList.addAll(c);
    }

    // Method 6
    // Inserts all of the elements in the specified
    // collection into this list, starting at the specified
    // position
    public boolean addAll(int index, Collection<?> c)
    {
        return roleUnresolvedList.addAll(index, c);
    }

    // Method 7
    // Inserts all of the elements in the RoleUnresolvedList
    // specified into list, starting at the specified
    // position, in the order in which they are returned by
    // the Iterator of the RoleUnresolvedList specified.
    public boolean addAll(int index,
                          RoleUnresolvedList roleList)
    {
        return this.roleUnresolvedList.addAll(index,
                                              roleList);
    }

    // Method 8
    // Appends all the elements in the RoleUnresolvedList
    // specified to the end of the list, in the order in
    // which they are returned by the Iterator o the
    // RoleUnresolvedList specified.
    public boolean addAll(RoleUnresolvedList roleList)
    {
        return roleList.addAll(roleList);
    }

    // Method 9
    // Return a view of this list as a List<RoleUnresolved>
    public List<RoleUnresolved> asList()
    {
        return roleUnresolvedList.asList();
    }

    // Method 10
    // Replaces the element at the specified position in
    // this list with the specified element
    public Object set(int index, Object element)
    {
        return roleUnresolvedList.set(index, element);
    }

    // Method 11
    // Sets the element at the position
    // specified to be the unresolved role specified.
    public void set(int index, RoleUnresolved role)
    {
        roleUnresolvedList.set(index, role);
    }

    // Method 12
    // Main driver method
    public static void main(String[] arg)
        throws MalformedObjectNameException
    {
        // Creating object of GFG class
        GFG roleUnresolvedList = new GFG();

        // Creating a List object
        // Declaring List of type ObjectName
        List<ObjectName> rolelist1
            = new LinkedList<ObjectName>();

        // Adding elements to above object
        // Custom inputs
        rolelist1.add(
            new ObjectName("domain1", "key1", "value1"));
        rolelist1.add(
            new ObjectName("domain2", "key2", "value2"));
        roleUnresolvedList.add(
            0,
            new RoleUnresolved("rolename1", rolelist1, 1));

        // Creating another List object
        List<ObjectName> roleList2
            = new LinkedList<ObjectName>();

        // Adding elements to above object
        // Custom inputs
        roleList2.add(
            new ObjectName("domain3", "key3", "value3"));
        roleList2.add(
            new ObjectName("domain4", "key4", "value4"));
        roleUnresolvedList.add(
            1,
            new RoleUnresolved("rolename2", roleList2, 2));

        // Creating(declaring) object of type RoleUnresolved
        List<RoleUnresolved> list
            = roleUnresolvedList.asList();

        // Initialising variable count
        int index = 0;

        // Condition check using size() method in List
        while (index < list.size())

        {
            // Print the elements
            System.out.println(list.get(index++) + "\t");
        }

        // As the condition fails
        // jump to new line
        System.out.println();
    }
}
```

**Output**

```java
role name: rolename1; value: domain1:key1=value1, domain2:key2=value2; problem type: 1    
role name: rolename2; value: domain3:key3=value3, domain4:key4=value4; problem type: 2
```