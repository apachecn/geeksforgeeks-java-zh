# 用示例列出 Java 中的接口

> 原文:[https://www.geeksforgeeks.org/list-interface-java-examples/](https://www.geeksforgeeks.org/list-interface-java-examples/)

列表界面提供了一种存储有序集合的方法。是[集合](https://www.geeksforgeeks.org/collections-in-java-2/)的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。

![List-and-ArrayList-in-Java-Collection-Framework](img/44f83bbf17ed431ea2790361ae6372b3.png)

**声明:**列表界面声明为:

```
public interface List<E> extends Collection<E> ; 
```

**让我们详细说明**在列表类中创建对象或实例。**由于**列表**是[界面](https://www.geeksforgeeks.org/interfaces-in-java/)，因此不能在类型列表中创建对象。为了创建一个对象，我们总是需要一个实现这个**列表**的类。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)后，可以限制列表中可以存储的对象类型。就像其他几个由用户定义的“*类*”实现的用户定义的“*接口一样， ***列表*** 是一个“*接口”，由*在 java.util 包中预定义的 ***数组列表**类实现。****

**语法:**这种类型的安全列表可以定义为:

```
List<Obj> list = new ArrayList<Obj> (); 
```

> **注意:** Obj 是要存储在列表中的对象的类型

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Demonstrate List Interface

// Importing alll utility classes
import java.util.*;

// Main class
// ListDemo class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List interface
         // implemented by the ArrayList class
        List<Integer> l1 = new ArrayList<Integer>();

        // Adding elements to object of List interface
        // Custom inputs

        l1.add(0, 1);
        l1.add(1, 2);

        // Print the elements inside the object
        System.out.println(l1);

        // Now creating another object of the List
        // interface implemented ArrayList class
        // Declaring object of integer type
        List<Integer> l2 = new ArrayList<Integer>();

        // Again adding elements to object of List interface
        // Custom inputs
        l2.add(1);
        l2.add(2);
        l2.add(3);

        // Will add list l2 from 1 index
        l1.addAll(1, l2);

        System.out.println(l1);

        // Removes element from index 1
        l1.remove(1);

        // Printing the updated List 1
        System.out.println(l1);

        // Prints element at index 3 in list 1
        // using get() method
        System.out.println(l1.get(3));

        // Replace 0th element with 5
        // in List 1
        l1.set(0, 5);

        // Again printing the updated List 1
        System.out.println(l1);
    }
}
```

**Output**

```
[1, 2]
[1, 1, 2, 3, 2]
[1, 2, 3, 2]
2
[5, 2, 3, 2]
```

现在让我们使用列表界面执行各种操作，以便更好地理解它们。我们将讨论下面列出的操作以及稍后通过干净的 java 代码实现的操作。

### 列表界面中的操作

因为列表是一个接口，所以它只能与实现该接口的类一起使用。现在，让我们看看如何在列表上执行一些常用的操作。

*   **操作 1:** 使用 add()方法向 List 类添加元素
*   **操作 2:** 使用 set()方法更新 List 类中的元素
*   **操作 3:** 使用 remove()方法移除元素

现在让我们单独讨论这些操作，并在代码中实现相同的操作，以便更好地掌握它。

**操作 1:** 使用 add()方法向 List 类添加元素

为了给列表添加一个元素，我们可以使用 [add()方法](https://www.geeksforgeeks.org/java-util-list-add-method-java/?ref=rp)。此方法被重载以基于不同的参数执行多个操作。

**参数:**取 2 个参数，即:

*   **添加(对象):**此方法用于在列表末尾添加一个元素。
*   **add(int index，Object):** 此方法用于在列表中的特定索引处添加元素

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Add Elements to a List

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of List interface,
        // implemented by ArrayList class
        List<String> al = new ArrayList<>();

        // Adding elements to object of List interface
        // Custom elements
        al.add("Geeks");
        al.add("Geeks");
        al.add(1, "For");

        // Print all the elements inside the
        // List interface object
        System.out.println(al);
    }
}
```

**Output**

```
[Geeks, For, Geeks]
```

**操作 2:** 更新元素

添加元素后，如果我们想更改元素，可以使用 [set()](https://www.geeksforgeeks.org/abstractlist-set-method-in-java-with-examples/) 方法来完成。因为列表是有索引的，所以我们想要更改的元素由元素的索引来引用。因此，此方法采用一个索引和需要插入该索引的更新元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Update Elements in a List

// Importing utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an object of List interface
        List<String> al = new ArrayList<>();

        // Adding elements to object of List class
        al.add("Geeks");
        al.add("Geeks");
        al.add(1, "Geeks");

        // Display theinitial elements in List
        System.out.println("Initial ArrayList " + al);

        // Setting (updating) element at 1st index
        // using set() method
        al.set(1, "For");

        // Print and display the updated List
        System.out.println("Updated ArrayList " + al);
    }
}
```

**Output:** 

```
Initial ArrayList [Geeks, Geeks, Geeks]
Updated ArrayList [Geeks, For, Geeks]
```

**操作 3:** 去除元素

为了从列表中移除一个元素，我们可以使用[移除()方法](https://www.geeksforgeeks.org/list-removeobject-obj-method-in-java-with-examples/)。此方法被重载以基于不同的参数执行多个操作。它们是:

**参数:**

*   **移除(对象):**此方法用于简单地从列表中移除对象。如果有多个这样的对象，则删除第一个出现的对象。
*   **remove(int index):** 由于一个列表是被索引的，所以这个方法采用一个整数值，这个整数值简单地删除列表中特定索引处的元素。移除元素后，所有元素都被移动到左边以填充空间，并且对象的索引被更新。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Remove Elements from a List

// Importing List and ArrayList classes
// from java.util package
import java.util.ArrayList;
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating List class object
        List<String> al = new ArrayList<>();

        // Adding elements to the object
        // Custom inputs
        al.add("Geeks");
        al.add("Geeks");

        // Adding For at 1st indexes
        al.add(1, "For");

        // Print the initialArrayList
        System.out.println("Initial ArrayList " + al);

        // Now remove element from the above list
        // present at 1st index
        al.remove(1);

        // Print the List after removal of element
        System.out.println("After the Index Removal " + al);

        // Now remove the current object from the updated
        // List
        al.remove("Geeks");

        // Finally print the updated List now
        System.out.println("After the Object Removal "
                           + al);
    }
}
```

**Output:** 

```
Initial ArrayList [Geeks, For, Geeks]
After the Index Removal [Geeks, Geeks]
After the Object Removal [Geeks]
```

### 遍历列表

到目前为止，我们有一个非常小的输入大小，我们正在为每个实体手动操作。现在，让我们讨论各种方法，通过这些方法，我们可以在列表中进行迭代，从而获得更大的采样集。

**方法:**遍历列表有多种方式。最著名的方法是使用基本的 [for loop](https://www.geeksforgeeks.org/loop-java-important-points/) 结合 [get()方法](https://www.geeksforgeeks.org/list-get-method-java-examples/)获取特定索引处的元素，以及 [advanced for loop](https://www.geeksforgeeks.org/for-each-loop-in-java/) 。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Iterate the Elements
// in an ArrayList

// Importing java utility classes
import java.util.*;

// Main class
public class GFG {

    // main driver method
    public static void main(String args[])
    {
        // Creating an empty Arraylist of string type
        List<String> al = new ArrayList<>();

        // Adding elements to above object of ArrayList
        al.add("Geeks");
        al.add("Geeks");

        // Adding element at specified position
        // inside list object
        al.add(1, "For");

        // Using  for loop for iteration
        for (int i = 0; i < al.size(); i++) {

            // Using get() method to
            // access particular element
            System.out.print(al.get(i) + " ");
        }

        // New line for better readability
        System.out.println();

        // Using for-each loop for iteration
        for (String str : al)

            // Printing all the elements
            // which was inside object
            System.out.print(str + " ");
    }
}
```

**Output:** 

```
Geeks For Geeks 
Geeks For Geeks
```

### 列表界面的方法

由于不同类型列表背后的主要概念是相同的，因此列表界面包含以下方法:

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [**添加(int index，element)**](https://www.geeksforgeeks.org/list-addint-index-e-element-method-in-java/) | 此方法用于在列表中的特定索引处添加元素。当传递单个参数时，它只是在列表的末尾添加元素。 |
| [**addAll(int index，Collection collection)**](https://www.geeksforgeeks.org/list-addall-method-in-java-with-examples/) | 此方法用于将给定集合中的所有元素添加到列表中。当传递单个参数时，它会在列表的末尾添加给定集合的所有元素。 |
| [**大小()**](https://www.geeksforgeeks.org/list-size-method-in-java-with-examples/) | 此方法用于返回列表的大小。 |
| [**晴()**](https://www.geeksforgeeks.org/list-clear-method-in-java-with-examples/) | 此方法用于移除列表中的所有元素。但是，创建的列表的引用仍然被存储。 |
| [**移除(int index)**](https://www.geeksforgeeks.org/list-removeint-index-method-in-java-with-examples/) | 此方法从指定的索引中移除元素。它将后续元素(如果有)向左移动，并将它们的索引减少 1。 |
| **移除(元素)** | 此方法用于移除列表中给定元素的第一个匹配项。 |
| [**获得(int 指数)**](https://www.geeksforgeeks.org/list-get-method-in-java-with-examples/) | 此方法返回指定索引处的元素。 |
| [**集合(int index，element)**](https://www.geeksforgeeks.org/arraylist-set-method-in-java-with-examples/) | 此方法用新元素替换给定索引处的元素。该函数返回刚刚被新元素替换的元素。 |
| [**【元素指数】**](https://www.geeksforgeeks.org/list-indexof-method-in-java-with-examples/) | 此方法返回给定元素的第一次出现，如果列表中没有该元素，则返回 *-1* 。 |
| [**【元素的最后索引】**](https://www.geeksforgeeks.org/list-lastindexof-method-in-java-with-examples/) | 此方法返回给定元素的最后一次出现，如果列表中没有该元素，则返回 *-1* 。 |
| **等于(元素)** | 此方法用于比较给定元素与列表元素的相等性。 |
| **hashCode()** | 此方法用于返回给定列表的 hashcode 值。 |
| **【isempty()** | 此方法用于检查列表是否为空。如果列表为空，则返回 true，否则返回 false。 |
| **含有(元素)** | 此方法用于检查列表是否包含给定的元素。如果列表包含元素，则返回 true。 |
| [**containsAll(集合集合)**](https://www.geeksforgeeks.org/list-containsall-method-in-java-with-examples/) | 此方法用于检查列表是否包含所有元素集合。 |
| **排序(比较器比较)** | 该方法用于根据给定的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)对列表中的元素进行排序。 |

</figure>

### **带有列表界面的类关联**

现在，让我们讨论实现列表界面的类，首先请参考下面的图示，以便更好地理解列表界面。具体如下:

![List-ArrayList-in-Java-In-Depth-Study](img/9b5d4717a0bb9dd15d6dc598671940cb.png)

[抽象列表](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)、[copy onwriterarraylist](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)和[抽象顺序列表](https://www.geeksforgeeks.org/abstractsequentiallist-in-java-with-examples/)是实现列表接口的类。在每个提到的类中都实现了一个单独的功能。它们如下:

1.  **抽象列表:**这个类用来实现一个不可修改的列表，对于这个列表只需要扩展这个抽象列表类，只需要实现 *get()* 和 *size()* 方法。
2.  **copy onwriterarraylist:**这个类实现了列表接口。这是[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)的增强版本，其中所有的修改(添加、设置、删除等。)是通过制作列表的新副本来实现的。
3.  **抽象顺序列表:**这个类实现了[集合接口](https://www.geeksforgeeks.org/collections-in-java-2/)和抽象集合类。这个类用来实现一个不可修改的列表，为此只需要扩展这个抽象列表类，只需要实现 *get()* 和 *size()* 方法。

我们将以这种方式进行。

*   数组列表
*   矢量
*   堆
*   链接列表

让我们按顺序讨论它们，并实现它们，以便用 List 接口弄清楚类的工作方式。

**第 1 类:数组列表**

[**【ArrayList】**](https://www.geeksforgeeks.org/arraylist-in-java/)**类在集合框架中实现，为我们提供了 Java 中的动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。让我们看看如何使用这个类创建一个列表对象。**

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the
// creation of list object using the
// ArrayList class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Size of ArrayList
        int n = 5;

        // Declaring the List with initial size n
        List<Integer> arrli
            = new ArrayList<Integer>(n);

        // Appending the new elements
        // at the end of the list
        for (int i = 1; i <= n; i++)
            arrli.add(i);

        // Printing elements
        System.out.println(arrli);

        // Remove element at index 3
        arrli.remove(3);

        // Displaying the list after deletion
        System.out.println(arrli);

        // Printing elements one by one
        for (int i = 0; i < arrli.size(); i++)
            System.out.print(arrli.get(i) + " ");
    }
}
```

****Output:** 

```
[1, 2, 3, 4, 5]
[1, 2, 3, 5]
1 2 3 5
```** 

****类 2:** [**矢量**](https://www.geeksforgeeks.org/java-util-vector-class-java/)**

**Vector 是一个在集合框架中实现的类，它实现了一个可增长的对象数组。Vector 实现了一个动态数组，这意味着它可以根据需要增长或收缩。像数组一样，它包含可以使用整数索引访问的组件。向量基本上属于遗留类，但现在它与集合完全兼容。让我们看看如何使用这个类创建一个列表对象。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the
// creation of list object using the
// Vector class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Size of the vector
        int n = 5;

        // Declaring the List with initial size n
        List<Integer> v = new Vector<Integer>(n);

        // Appending the new elements
        // at the end of the list
        for (int i = 1; i <= n; i++)
            v.add(i);

        // Printing elements
        System.out.println(v);

        // Remove element at index 3
        v.remove(3);

        // Displaying the list after deletion
        System.out.println(v);

        // Printing elements one by one
        for (int i = 0; i < v.size(); i++)
            System.out.print(v.get(i) + " ");
    }
}
```

****Output:** 

```
[1, 2, 3, 4, 5]
[1, 2, 3, 5]
1 2 3 5
```** 

****3 级:** [**叠加**](https://www.geeksforgeeks.org/stack-class-in-java/)**

**栈是在集合框架中实现的类，扩展了向量类模型，实现了[栈数据结构](https://www.geeksforgeeks.org/stack-data-structure/)。该课程基于后进先出的基本原则。除了基本的推送和弹出操作，该类还提供了空、搜索和查看三个功能。让我们看看如何使用这个类创建一个列表对象。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the
// creation of list object using the
// Stack class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Size of the stack
        int n = 5;

        // Declaring the List
        List<Integer> s = new Stack<Integer>();

        // Appending the new elements
        // at the end of the list
        for (int i = 1; i <= n; i++)
            s.add(i);

        // Printing elements
        System.out.println(s);

        // Remove element at index 3
        s.remove(3);

        // Displaying the list after deletion
        System.out.println(s);

        // Printing elements one by one
        for (int i = 0; i < s.size(); i++)
            System.out.print(s.get(i) + " ");
    }
}
```

****Output:** 

```
[1, 2, 3, 4, 5]
[1, 2, 3, 5]
1 2 3 5
```** 

****4 级:** [**链接列表**](https://www.geeksforgeeks.org/linked-list-in-java/)**

**LinkedList 是一个在集合框架中实现的类，集合框架本身就实现了[链表数据结构](https://www.geeksforgeeks.org/data-structures/linked-list/)。它是一种线性数据结构，其中元素不存储在连续的位置，每个元素都是一个独立的对象，有数据部分和地址部分。这些元素使用指针和地址进行链接。每个元素都被称为一个节点。由于插入和删除的动态性和容易性，它们比数组更受欢迎。让我们看看如何使用这个类创建一个列表对象。**

****示例:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the
// creation of list object using the
// LinkedList class

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Size of the LinkedList
        int n = 5;

        // Declaring the List with initial size n
        List<Integer> ll = new LinkedList<Integer>();

        // Appending the new elements
        // at the end of the list
        for (int i = 1; i <= n; i++)
            ll.add(i);

        // Printing elements
        System.out.println(ll);

        // Remove element at index 3
        ll.remove(3);

        // Displaying the list after deletion
        System.out.println(ll);

        // Printing elements one by one
        for (int i = 0; i < ll.size(); i++)
            System.out.print(ll.get(i) + " ");
    }
}
```

****Output:** 

```
[1, 2, 3, 4, 5]
[1, 2, 3, 5]
1 2 3 5
```**