# 实现 CopyOnWriteArraySet API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-copy onwriterarrayset-API/](https://www.geeksforgeeks.org/java-program-to-implement-copyonwritearrayset-api/)

**copy onwriterarrayset**是 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的成员。这是一个使用内部[副本写数组列表](https://www.geeksforgeeks.org/copyonwritearraylist-in-java/)进行所有操作的集合。它是在 JDK 1.5 中引入的，我们可以说它是 Set 的线程安全版本。要使用这个类，我们需要从 **java.util.concurrent** 包导入它。

![](img/1ea8eef8e633f77848d9d4cd0dde300d.png)

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement CopyOnWriteArraySet API

// Importing required utility classes
//  from java.util package
import java.util.Collection;
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;
import java.util.concurrent.CopyOnWriteArraySet;

// CopyOnWriteArraySetImpl
public class<E> GFG {
    private CopyOnWriteArraySet<E> copyOnWriteArraySet;

    // Constructor oof this class
    public GFG()
    {

        // Creating an empty set
        copyOnWriteArraySet = new CopyOnWriteArraySet<E>();
    }

    // Creates a set containing all of the elements
    // of the specified collection
    public GFG(Collection<? extends E> c)
    {
        copyOnWriteArraySet = new CopyOnWriteArraySet<E>(c);
    }

    // Method
    // To add the specified element into list
    // if not already present
    public boolean add(E eobj)
    {
        return copyOnWriteArraySet.add(eobj);
    }

    // Method
    // Returning true if there is a specified element
    // present in the list
    public boolean contains(Object obj)
    {
        return copyOnWriteArraySet.contains(obj);
    }

    // Method
    // Returning true if the set is empty
    public boolean isEmpty()
    {
        return copyOnWriteArraySet.isEmpty();
    }

    // Method
    // To traverse over the elements
    // present in the set
    public Iterator<E> iterator()
    {
        return copyOnWriteArraySet.iterator();
    }

    // Method
    // To remove the specified element
    // present in the Set
    public boolean remove(Object obj)
    {
        return copyOnWriteArraySet.remove(obj);
    }

    // Method
    // Returning the number of elements
    // present in the set
    public int size() { return copyOnWriteArraySet.size(); }

    // Method
    // Removing all elements from the given set
    public void clear() { copyOnWriteArraySet.clear(); }

    // Method
    // Returning an array containing all of the elements
    // present in this set
    public Object[] toArray()
    {
        return copyOnWriteArraySet.toArray();
    }

    // Method
    // Now, adding all of the elements in the specified
    // collection to this set if they're not already present
    public boolean addAll(Collection<? extends E> c)
        throws UnsupportedOperationException,
               ClassCastException, NullPointerException,
               IllegalArgumentException
    {
        return copyOnWriteArraySet.addAll(c);
    }

    // Method
    // Returns only the elements in this set that are
    // contained in the specified collection
    public boolean retainAll(Collection<?> c)
        throws UnsupportedOperationException,
               ClassCastException, NullPointerException
    {
        return copyOnWriteArraySet.retainAll(c);
    }

    // Method
    // Removes from this set the elements that are contained
    // in the specified collection
    public boolean removeAll(Collection<?> c)
        throws UnsupportedOperationException,
               NullPointerException, ClassCastException
    {
        return copyOnWriteArraySet.retainAll(c);
    }

    // Returns an array containing all of the elements in
    // this set.

    public <T> T[] toArray(T[] a)
        throws ArrayStoreException, NullPointerException
    {
        return copyOnWriteArraySet.toArray(a);
    }

    // Method
    // Main driver Method
    public static void main(String args[])
    {
        // Creating an object of above class (GFG class)
        // Declaring object of integer type
        GFG<Integer> copyOnWriteArraySet
            = new GFG<Integer>();

        // Adding custom input elements after condition
        // check

        // Custom input elements are added
        // using the add() method
        if (copyOnWriteArraySet.add(12))
            System.out.println("Element 12 added to Set");
        if (copyOnWriteArraySet.add(13))
            System.out.println("Element 13 added to Set");
        if (copyOnWriteArraySet.add(14))
            System.out.println("Element 14 added to Set");
        if (copyOnWriteArraySet.add(15))
            System.out.println("Element 15 added to Set");

        // Print and display the current size of Set
        System.out.println(
            "The size of copyOnWriteArraySet is "
            + copyOnWriteArraySet.size());

        // Checking whrtjer the Set contains element
        //  using the contains() method
        if (copyOnWriteArraySet.contains(14))
            System.out.println(
                "The copyOnWriteArraySet contains 14");
        else

            System.out.println(
                "The copyOnWriteArraySet does not contain 14");

        // Removing element from the Set
        // using remove() method
        if (copyOnWriteArraySet.remove(13))

            // Print desired element is removed
            System.out.println("Element 13 removed");
        else

            // Print desired element is not removed
            System.out.println("Element 13 not removed");

        // Now, print and display the elements
        System.out.println(
            "The element of copyOnWriteArraySet are");
        Iterator<Integer> iterator
            = copyOnWriteArraySet.iterator();

        // Condition holds true til there is
        // single element remaining
        while (iterator.hasNext()) {

            // Print and display all elements size
            System.out.print(iterator.next() + "\t");
        }

        // Appendind a new line for better readability
        System.out.println();

        // Creating an object of Set class of integer type
        Set<Integer> removedSet = new HashSet<Integer>();

        // Custom input entries to above Set
        removedSet.add(12);
        removedSet.add(13);

        // Display message only
        System.out.println("The elements after removing");

        // removeAll()  method wipes off all elements
        // that was present in Set object
        copyOnWriteArraySet.removeAll(removedSet);

        // Iterator to traverse the elements
        Iterator<Integer> riterator
            = copyOnWriteArraySet.iterator();

        // Again condition holds true till there is
        // single elemennt remaining in the List
        while (riterator.hasNext()) {

            // Printing the elements in the object
            // using the next() method
            System.out.print(riterator.next() + "\t");
        }

        // New line
        System.out.println();

        // Removing all elements from the Set using clear()
        // method
        copyOnWriteArraySet.clear();

        // Display message to showcase all elements are
        // removed
        System.out.println(
            "copyOnWriteArraySet Elements are completely removed");

        // Lastly, verifying whether the Set is empty or not
        if (copyOnWriteArraySet.isEmpty())

            // Print statement if no elements in Set
            System.out.println(
                "copyOnWriteArraySet is empty");
        else

            // Print statement if elements found in Set
            System.out.println(
                "copyOnWriteArraySet is not empty");
    }
}
```

**输出:**

```java
Element 12 added to Set
Element 13 added to Set
Element 14 added to Set
Element 15 added to Set
The size of copyOnWriteArraySet is 4
The copyOnWriteArraySet contains 14
Element 13 removed
The element of copyOnWriteArraySet are
12    14    15    
The elements after removing
12    
copyOnWriteArraySet Elements are completely removed
copyOnWriteArraySet is empty

```