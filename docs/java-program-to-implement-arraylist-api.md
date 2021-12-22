# 实现数组列表 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-arraylist-api/](https://www.geeksforgeeks.org/java-program-to-implement-arraylist-api/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是列表界面的一个可调整大小的数组。它提供了在需要时可以用来操作数组大小的方法。

数组列表的每个实例都有一定的容量，容量意味着数组列表中存储元素的大小。如果您没有分配任何容量，那么默认容量是 10，但是如果您输入第 11 个元素，那么它将根据您的要求自动增加阵列的容量，因为数组列表是一个可增长的列表。

数组列表的一些操作，比如 size()，isEmpty()，get()，set()，iterator()，和 ListIterator()都是在常量时间内运行的。add 操作在 n 个时间内运行，n 是调用 add 方法的次数或在数组中添加元素的次数。

**数组列表的构造函数:**

1.  **数组列表():**最初创建一个空的数组列表。
2.  **数组列表(集合<？扩展 E>c:**创建一个包含给定集合元素的数组列表。

**数组列表 API 的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement ArrayList API

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Iterator;
import java.util.List;
import java.util.ListIterator;
import java.util.Spliterator;

public class ArrayListIntegerExample {
    public static void main(String[] args)
    {
        // Construct an ArrayList having default capacity 10
        ArrayList<Integer> array = new ArrayList<>();

        // ArrayList(Collection <? extends E> c)
        ArrayList<Integer> arrayWithColl
            = new ArrayList<Integer>(array);

        // Add elements in array
        array.add(100);
        array.add(120);
        array.add(500);
        array.add(220);
        array.add(150);

        //  Insert the elements in specified index
        // array.add(index, element);
        array.add(4, 50);

        // Add all the elements together
        // array.addAll(collection)
        List<Integer> list;

        list = new ArrayList<Integer>(Arrays.asList(90, 20, 40, 10, 15));
        array.addAll(list);

        // Add all the elements in specified index
        // array.addAll(index, collection)
        list = new ArrayList<Integer>(Arrays.asList(60, 25, 12, 16, 45));

        array.addAll(2, list);

        // Create shallow copy of array
        ArrayList<Integer> array1;

        array1 = array;

        // Clear all the element from the list
        array.clear();

        // Check whether the particular element is present
        // in the list or not array.contains(object)
        array1.add(100);
        array1.add(120);
        array1.add(500);
        array1.add(220);
        array1.add(150);

        System.out.println("Contains 120? : "
            + array1.contains(120)); // returns true
        System.out.println("Contains 200? : "
            + array1.contains(200)); // returns false

        // To ensure the minimum capacity of array
        // ArrayList<E> arrayname = new ArrayList<E>(int
        // minCapacity)
        ArrayList<Integer> array2 = new ArrayList<Integer>(10);

        // Iterate through the ArrayList

        System.out.println();
        System.out.println("Elements of the array using enhanced for-loop : ");

        array.forEach(i -> System.out.print(i + " "));
        System.out.println();

        // Iterator
        System.out.println("Elements of the array using iterator : ");

        Iterator<Integer> itr = array.iterator();

        while (itr.hasNext())
            System.out.print(itr.next() + " ");

        System.out.println();

        // List Iterator
        System.out.println("Elements of array using list - iterator : ");

        ListIterator<Integer> itr1 = array.listIterator();

        while (itr1.hasNext())
            System.out.print(itr1.next() + " ");

        System.out.println();

        // Get the particular element from specified index
        // array.get(index)
        System.out.println("Element at index 2 is : "
                           + array.get(2));

        System.out.println();

        // Get the position of particular element
        // array.indexOf(object)
        System.out.println("Element 500 is at index position : "
            + array.indexOf(500));

        System.out.println();

        // Check whether list is empty or not
        System.out.println("Array is empty? "
                           + array.isEmpty());

        System.out.println();

        // Get the last index of element in array
        // array.lastIndexOf(object)
        System.out.println("Last index of the element 100 is : "
            + array.lastIndexOf(100));

        System.out.println();

        // Remove the particular element
        // array.remove(index)
        System.out.println("Remove the element which is at index 3 : "
            + array.remove(3));

        System.out.println();

        // Remove all the elements together
        // array.removeAll(collection)
        array.removeAll(array);

        // Remove all the elements of the collection
        // if condition specified the given predicate
        array1.add(100);
        array1.add(120);
        array1.add(500);
        array1.add(220);
        array1.add(150);
        array1.add(123);
        array1.add(233);
        array1.add(111);

        array1.removeIf(num -> (num % 3 == 0));
        System.out.println("Array element after filtering : " + array1);

        System.out.println();

        // Retain all the elements
        array1.retainAll(array);

        System.out.println("Retain the array element : "
                           + array1);

        System.out.println();

        // Set the element at particular index
        array1.set(3, 999);

        System.out.println();

        // Display the size of arraylist
        System.out.println("Size of the array is : "
                           + array1.size());

        System.out.println();

        // Sort the list
        Collections.sort(array1);

        System.out.println("Array elements after sorting : "
                           + array1);

        System.out.println();

        // Create a late-binding
        Spliterator<Integer> split = array1.spliterator();

        // characteristic
        if (split.hasCharacteristics(Spliterator.ORDERED))
            System.out.println("Ordered");

        if (split.hasCharacteristics(Spliterator.SIZED))
            System.out.println("Sized");

        System.out.println();

        // estimateSize() and getExactSizeIfKnown
        System.out.println("Estimate size of arraylist is : "
            + split.estimateSize());
        System.out.println("Exact size of array is : "
                           + split.getExactSizeIfKnown());

        System.out.println();

        // trySplit
        Spliterator<Integer> split1 = split.trySplit();
        split.forEachRemaining(i -> System.out.println(i));

        System.out.println("*****");
        split1.forEachRemaining(i -> System.out.println(i));

        System.out.println();

        // Returns a sub-list within a specified index
        System.out.println("Sub-list from the index position 1 to 3 : "
            + array1.subList(1, 3));

        System.out.println();

        // Returns an array that contain all elements
        // public Object[] toArray()
        Object[] o = array1.toArray();

        System.out.println("ArrayList traversal using toArray method : "
            + Arrays.toString(o));

        System.out.println();

        // public <T> T[] toArray(T[] a)
        Integer a[] = new Integer[array1.size()];

        a = array1.toArray(a);
        System.out.println(
          "ArrayList traversal using toArray with argument method : "
            + Arrays.toString(a));

        System.out.println();

        // Trim the size to the number of elements
        array1.trimToSize();

        System.out.println("Array size after trimming : "
                           + array1.size());
    }
}
```

**Output**

```java
Contains 120? : true
Contains 200? : false

Elements of the array using enhanced for-loop : 
100 120 500 220 150 
Elements of the array using iterator : 
100 120 500 220 150 
Elements of array using list - iterator : 
100 120 500 220 150 
Element at index 2 is : 500

Element 500 is at index position : 2

Array is empty? false

Last index of the element 100 is : 0

Remove the element which is at index 3 : 220

Array element after filtering : [100, 500, 220, 233]

Retain the array element : [100, 500, 220, 233]

Size of the array is : 4

Array elements after sorting : [100, 220, 500, 999]

Ordered
Sized

Estimate size of arraylist is : 4
Exact size of array is : 4

500
999
*****
100
220

Sub-list from the index position 1 to 3 : [220, 500]

ArrayList traversal using toArray method : [100, 220, 500, 999]

ArrayList traversal using toArray with argument method : [100, 220, 500, 999]

Array size after trimming : 4
```