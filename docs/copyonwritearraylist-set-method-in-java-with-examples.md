# Java 中的 CopyOnWriteArrayList set()方法，带示例

> 原文:[https://www . geeksforgeeks . org/copy onwriterarraylist-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/copyonwritearraylist-set-method-in-java-with-examples/)

类[中的 **set(E e)** 方法将指定索引处的元素替换为作为方法参数提供的元素。方法返回已被新元素替换的元素。
**语法:**](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/) 

```
public E set(int index, E element)
```

**参数:**该方法取下述两个参数:

*   **索引**:包含新元素替换现有元素的位置。强制添加。
*   **元素**:包含要替换的新元素。

**返回值:**该方法返回已经被替换的**元素**。
**异常:**方法抛出**indexout of boundsexception**当方法的索引小于 0 或大于列表的大小时发生。
下面是一些程序来说明 CopyOnWriteArrayList.set()方法的使用:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the use of set() method

import java.util.concurrent.CopyOnWriteArrayList;

public class CopyOnWriteArrayListDemo {
    public static void main(String[] args)
    {

        // creating an ArrayList
        CopyOnWriteArrayList<String> arrayList
            = new CopyOnWriteArrayList<String>();

        // Adding elements to the list
        arrayList.add(0, "geeks");
        arrayList.add(1, "for");
        arrayList.add(2, "geeksforgeeks");

        // before invoking the set() method
        System.out.println("CopyOnWriteArrayList: "
                           + arrayList);

        // invoking the set() method
        String returnValue
            = arrayList.set(0, "toodles");

        // printing the returned value
        System.out.println("The value returned "
                           + "on calling set() method:"
                           + returnValue);

        // print CopyOnWriteArrayList
        System.out.println("CopyOnWriteArrayList "
                           + "after calling set():"
                           + arrayList);
    }
}
```

![](img/9f76e815d737809cf5f098022685cb5f.png)

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to illustrate the ArrayIndexOutOfBoundsException

import java.util.concurrent.CopyOnWriteArrayList;

public class CopyOnWriteArrayListDemo {
    public static void main(String[] args)
    {

        // creating an ArrayList
        CopyOnWriteArrayList<String> arrayList
            = new CopyOnWriteArrayList<String>();

        // Adding elements to the list
        arrayList.add(0, "geeks");
        arrayList.add(1, "for");
        arrayList.add(2, "geeksforgeeks");

        // before invoking the set() method
        System.out.println("CopyOnWriteArrayList: "
                           + arrayList);

        try {

            System.out.println("Trying to add "
                               + "element at index 4 "
                               + "using set() method");

            // invoking the set() method
            String returnValue
                = arrayList.set(4, "toodles");
            // printing the returned value
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

![](img/387a27fa4cda91f0bbcdfe5ba0c5fac7.png)