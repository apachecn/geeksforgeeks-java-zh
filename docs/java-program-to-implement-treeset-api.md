# 实现树集应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-treeset-api/](https://www.geeksforgeeks.org/java-program-to-implement-treeset-api/)

[**TreeSet**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Java 中**[**sorted set**](https://www.geeksforgeeks.org/sortedset-java-examples/)接口最重要的实现之一，该接口使用 [**Tree**](https://www.geeksforgeeks.org/binary-tree-data-structure/) 进行存储。无论是否提供明确的 [**比较器**](https://www.geeksforgeeks.org/comparator-interface-java/) ，元素的顺序都由集合使用它们的自然顺序来维护。要正确实现 [**设置界面**](https://www.geeksforgeeks.org/set-in-java/) ，这必须与等号一致。它也可以由设置创建时提供的比较器排序，具体取决于使用的构造函数。现在，在实现 TreeSet API 时，任务分为两部分:**

1.  **创建一个类，包含它的树集的所有方法都被命名为“树集实现”**
2.  **实现上述树集应用编程接口**

****过程:**用树集合的所有方法创建一个类**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program illustrating TreeSet API by creating
// all the methods of TreeSet API

// Class 
// TreeSetImplementation class implement the TreeSet API
class TreeSetImplementation<E> {

    // New TreeSet
    private TreeSet<E> set;

    // Constructor creates a new empty TreeSet, sorted
    // according to its natural ordering
    public TreeSetImplementation()
    {
        // Create a TreeSet
        set = new TreeSet<E>();
    }

    // Constructor creates a new TreeSet of type E, sorted
    // according to its natural ordering
    public TreeSetImplementation(
        Collection<? extends E> obj)
    {
        // Create a TreeSet
        set = new TreeSet<E>(obj);
    }

    // Constructor creates a new TreeSet of type E, sorted
    // according to specified comparator
    public TreeSetImplementation(
        Comparator<? super E> comparator)
    {
        // Create a TreeSet
        set = new TreeSet<E>(comparator);
    }

    // Constructor creates a new tree set containing the
    // same elements and using the same ordering as the
    // specified sorted set
    public TreeSetImplementation(SortedSet<E> set1)
    {
        set = new TreeSet<E>(set1);
    }

    // Adds element to the TreeSet
    public boolean add(E ele) { return set.add(ele); }

    // Adds all of the elements in the specified collection
    // to the set
    public boolean addAll(Collection<? extends E> colle)
    {
        return set.addAll(colle);
    }

    // Removes all of the elements from the set
    public void clear() { set.clear(); }

    // Returns a shallow copy of the TreeSet instance
    public Object clone() { return set.clone(); }

    // Returns the comparator
    public Comparator<? super E> comparator()
    {
        return set.comparator();
    }

    // Returns true if the set contains the specified
    // element
    public boolean contains(Object obj)
    {
        return set.contains(obj);
    }

    // Returns an iterator in descending order
    public Iterator<E> descendingIterator()
    {
        return set.descendingIterator();
    }

    // Returns a reverse order view of the elements
    // contained in the set
    public NavigableSet<E> descendingSet()
    {
        return set.descendingSet();
    }

    // Returns the first (lowest) element currently in the
    // set
    public E first() { return set.first(); }

    // Returns the greatest element in the set less than or
    // equal to the given element, or null if it is not
    // present in the set
    public E floor(E ele) { return set.floor(ele); }

    // Returns the least element in the set greater than or
    // equal to the given element, or null if it is not
    // present in the set
    public E ceiling(E ele) { return set.ceiling(ele); }

    // Returns a view of the portion of the set whose
    // elements are strictly less than to specified element
    public SortedSet<E> headSet(E ele)
    {
        return set.headSet(ele);
    }

    // Returns a view of the portion of the set whose
    // elements are less than or
    // equal to specified element
    public NavigableSet<E> headSet(E ele, boolean inclusive)
    {
        return set.headSet(ele, inclusive);
    }

    // Returns the least element in the set strictly greater
    // than the given element, or null if there is no such
    // element.
    public E higher(E ele) { return set.higher(ele); }

    // Returns true if the set is empty
    public boolean isEmpty() { return set.isEmpty(); }

    // Returns an iterator over the set in ascending order
    public Iterator<E> iterator() { return set.iterator(); }

    // Returns the last (highest) element currently in the
    // set
    public E last() { return set.last(); }
    // Returns the greatest element in the set strictly less
    // than the given element, or null if there is no such
    // element
    public E lower(E ele) { return set.lower(ele); }

    // Retrieves and removes the first (lowest) element, or
    // returns null if the set is empty
    public E pollFirst() { return set.pollFirst(); }
    // Retrieves and removes the last (highest) element, or
    // returns null if the set is empty
    public E pollLast() { return set.pollLast(); }

    // Removes the specified element from the set if it is
    // present
    public boolean remove(Object obj)
    {
        return set.remove(obj);
    }

    // Returns the size of the set
    public int size() { return set.size(); }

    // Returns a view of the portion of the set whose
    // elements range from lele to rele.
    public NavigableSet<E> subSet(E lele,
                                  boolean lInclusive,
                                  E rele,
                                  boolean rInclusive)
    {
        return set.subSet(lele, lInclusive, rele,
                          rInclusive);
    }

    // Returns a view of the portion of the set whose
    // elements range from lele (inclusive) to rele
    // (exclusive).
    public SortedSet<E> subSet(E lele, E rele)
    {
        return set.subSet(lele, rele);
    }

    // Returns a view of the portion of the set whose
    // elements are greater than or equal to ele.

    public SortedSet<E> tailSet(E ele)
    {
        return set.tailSet(ele);
    }

    // Returns a view of the portion of the set whose
    // elements are greater than (or equal to, if inclusive
    // is true) else false
    public NavigableSet<E> tailSet(E ele, boolean inclusive)
    {
        return set.tailSet(ele, inclusive);
    }
}
```

****实现:**T2】树集 API**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program demonstrate TreeSet API
import java.util.Collection;
import java.util.Comparator;
import java.util.Iterator;
import java.util.NavigableSet;
import java.util.SortedSet;
import java.util.TreeSet;

// Class
class TreeSetImplementation<E> {

    // New TreeSet
    private TreeSet<E> set;

    // Constructor creates a new empty TreeSet, sorted
    // according to its natural ordering
    public TreeSetImplementation()
    {
        // Create a TreeSet
        set = new TreeSet<E>();
    }

    // Constructor creates a new TreeSet of type E, sorted
    // according to its natural ordering
    public TreeSetImplementation(
        Collection<? extends E> obj)
    {
        // Create a TreeSet
        set = new TreeSet<E>(obj);
    }

    // Constructor creates a new TreeSet of type E, sorted
    // according to specified comparator
    public TreeSetImplementation(
        Comparator<? super E> comparator)
    {
        // Create a TreeSet
        set = new TreeSet<E>(comparator);
    }

    // Constructor creates a new tree set containing the
    // same elements and using the same ordering as the
    // specified sorted set
    public TreeSetImplementation(SortedSet<E> set1)
    {
        set = new TreeSet<E>(set1);
    }

    // Adds element to the TreeSet
    public boolean add(E ele) { return set.add(ele); }

    // Adds all of the elements in the specified collection
    // to the set
    public boolean addAll(Collection<? extends E> colle)
    {
        return set.addAll(colle);
    }

    // Removes all of the elements from the set
    public void clear() { set.clear(); }

    // Returns a shallow copy of the TreeSet instance
    public Object clone() { return set.clone(); }

    // Returns the comparator
    public Comparator<? super E> comparator()
    {
        return set.comparator();
    }

    // Returns true if the set contains the specified
    // element
    public boolean contains(Object obj)
    {
        return set.contains(obj);
    }

    // Returns an iterator in descending order
    public Iterator<E> descendingIterator()
    {
        return set.descendingIterator();
    }

    // Returns a reverse order view of the elements
    // contained in the set
    public NavigableSet<E> descendingSet()
    {
        return set.descendingSet();
    }

    // Returns the first (lowest) element currently in the
    // set
    public E first() { return set.first(); }

    // Returns the greatest element in the set less than or
    // equal to the given element, or null if it is not
    // present in the set
    public E floor(E ele) { return set.floor(ele); }

    // Returns the least element in the set greater than or
    // equal to the given element, or null if it is not
    // present in the set
    public E ceiling(E ele) { return set.ceiling(ele); }

    // Returns a view of the portion of the set whose
    // elements are strictly less than to specified element
    public SortedSet<E> headSet(E ele)
    {
        return set.headSet(ele);
    }

    // Returns a view of the portion of the set whose
    // elements are less than or
    // equal to specified element
    public NavigableSet<E> headSet(E ele, boolean inclusive)
    {
        return set.headSet(ele, inclusive);
    }

    // Returns the least element in the set strictly greater
    // than the given element, or null if there is no such
    // element.
    public E higher(E ele) { return set.higher(ele); }

    // Returns true if the set is empty
    public boolean isEmpty() { return set.isEmpty(); }

    // Returns an iterator over the set in ascending order
    public Iterator<E> iterator() { return set.iterator(); }

    // Returns the last (highest) element currently in the
    // set
    public E last() { return set.last(); }
    // Returns the greatest element in the set strictly less
    // than the given element, or null if there is no such
    // element
    public E lower(E ele) { return set.lower(ele); }

    // Retrieves and removes the first (lowest) element, or
    // returns null if the set is empty
    public E pollFirst() { return set.pollFirst(); }
    // Retrieves and removes the last (highest) element, or
    // returns null if the set is empty
    public E pollLast() { return set.pollLast(); }

    // Removes the specified element from the set if it is
    // present
    public boolean remove(Object obj)
    {
        return set.remove(obj);
    }

    // Returns the size of the set
    public int size() { return set.size(); }

    // Returns a view of the portion of the set whose
    // elements range from lele to rele.
    public NavigableSet<E> subSet(E lele,
                                  boolean lInclusive,
                                  E rele,
                                  boolean rInclusive)
    {
        return set.subSet(lele, lInclusive, rele,
                          rInclusive);
    }

    // Returns a view of the portion of the set whose
    // elements range from lele (inclusive) to rele
    // (exclusive).
    public SortedSet<E> subSet(E lele, E rele)
    {
        return set.subSet(lele, rele);
    }

    // Returns a view of the portion of the set whose
    // elements are greater than or equal to ele.

    public SortedSet<E> tailSet(E ele)
    {
        return set.tailSet(ele);
    }

    // Returns a view of the portion of the set whose
    // elements are greater than (or equal to, if inclusive
    // is true) ele
    public NavigableSet<E> tailSet(E ele, boolean inclusive)
    {
        return set.tailSet(ele, inclusive);
    }
}

public class GFG {
    public static void main(String[] arg)
    {

        // Create a new TreeSet
        TreeSetImplementation<Integer> set
            = new TreeSetImplementation<Integer>();

        // Add elements
        set.add(10);
        set.add(30);
        set.add(20);
        set.add(40);
        set.add(50);

        // Iterateor for iterate over TreeSet
        Iterator<Integer> it = set.iterator();

        System.out.println("Elements of the TreeSet:");

        // Iterate using iterator
        while (it.hasNext()) {
            // Print element of the set
            System.out.print(it.next() + " ");
        }

        System.out.println();
        System.out.println();

        // Print size of the set
        System.out.println("Size of the set: "
                           + set.size());
        System.out.println();

        // Print ceiling of 45
        System.out.println("Ceiling of 45: "
                           + set.ceiling(45));
        System.out.println();

        // Descending iterator, Print in reverse order
        Iterator<Integer> revit = set.descendingIterator();
        System.out.println("The reverse order: ");
        while (revit.hasNext()) {
            System.out.print(revit.next() + "\t");
        }

        System.out.println();
        System.out.println();

        // Print first element in the set
        System.out.println("The first element in the set: "
                           + set.first());
        System.out.println();

        // Print floor value of 45
        System.out.println("Floor value of 45: "
                           + set.floor(45));
        System.out.println();

        // Print last element in the set
        System.out.println("The last element in the set: "
                           + set.last());
        System.out.println();

        // Remove 20 from the set
        set.remove(20);

        // Print the size of the set
        System.out.println("Size of the set: "
                           + set.size());
        System.out.println();

        // Print the headSet of 35
        System.out.println("HeadSet of 35: ");
        NavigableSet<Integer> set1 = set.headSet(35, true);
        Iterator<Integer> it1 = set1.iterator();
        while (it1.hasNext()) {
            System.out.println(it1.next() + " ");
        }
        System.out.println();

        // Print the subset between 5 and 45
        System.out.println("Subset between 5 and 45: ");
        set1 = set.subSet(5, true, 30, true);
        it1 = set1.iterator();
        while (it1.hasNext()) {
            System.out.println(it1.next() + "\t");
        }
        System.out.println();

        // Print the tailSet of 35
        System.out.println("The tailSet of 35: ");
        set1 = set.tailSet(35, true);
        it1 = set1.iterator();
        while (it1.hasNext()) {
            System.out.println(it1.next() + "\t");
        }

        System.out.println();
    }
}
```

****Output**

```
Elements of the TreeSet:
10 20 30 40 50 

Size of the set: 5

Ceiling of 45: 50

The reverse order: 
50    40    30    20    10    

The first element in the set: 10

Floor value of 45: 40

The last element in the set: 50

Size of the set: 4

HeadSet of 35: 
10 
30 

Subset between 5 and 45: 
10    
30    

The tailSet of 35: 
40    
50    
```**