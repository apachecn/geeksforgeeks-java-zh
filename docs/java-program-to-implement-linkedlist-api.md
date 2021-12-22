# 实现链接列表应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-linkedlist-api/](https://www.geeksforgeeks.org/java-program-to-implement-linkedlist-api/)

[链表](https://www.geeksforgeeks.org/linked-list-in-java/)是存在于 java.util 包中的集合框架的一部分。这个类是 LinkedList 数据结构的实现，linked list 数据结构是一种线性数据结构，其中元素不存储在连续的位置，每个元素都是一个单独的对象，有数据部分和地址部分。

什么是链表应用编程接口？

*   **Linked list API** aims to implement linked list collection as a part of the collection framework inherited from [java.util](https://www.geeksforgeeks.org/java-util-package-java/) package.
*   This API is a double linked list implementation of the list and deque interfaces.
*   The API implements all optional list operations and allows all elements (including null).
*   For the doubly linked list, all operations are performed as expected. The operation of indexing into the list will traverse the list from beginning to end, whichever is closer to the specified index.
*   The following is the source code of java program that implements LinkedList collection API.

**例:**

## 爪哇

```
// Java Program to Implement LinkedList API

// Importing utility classes from java.util package
import java.util.*;
import java.util.Collection;

// Class
// Main class consisting of all methods
public class LinkedListImpl<E> {

    // Member variable of this class
    private LinkedList<E> linkedList;

    // Constructors of this class

    // 1\. Default constructor
    public LinkedListImpl()
    {
        linkedList = new LinkedList<E>();
    }

    // 2\. Parameterized constructor
    public LinkedListImpl(Collection<? extends E> c)
    {
        linkedList = new LinkedList<E>(c);
    }

    // Method 1
    // To append specified element to end of this List
    public boolean add(E e)
    {

        // Returning the last element from the List
        return linkedList.add(e);
    }

    // Method 2
    // To insert specified element at
    // the specified position in this List
    public void add(int index, E element)
    {
        linkedList.add(index, element);
    }

    // Method 3
    // To add all the elements in this List
    public boolean addAll(Collection<? extends E> c)
    {
        return linkedList.addAll(c);
    }

    // Method 4
    // To add all the elements in this List
    public boolean addAll(int index,
                          Collection<? extends E> c)
    {
        return linkedList.addAll(index, c);
    }

    // Method 5
    // to inserts specified element at beginning of this
    // List
    public void addFirst(E e) { linkedList.addFirst(e); }

    // Method 6
    // To appends specified element to end of this List
    public void addLast(E e) { linkedList.addLast(e); }

    // Method 7
    // Removes all of the elements from this list.
    public void clear() { linkedList.clear(); }

    // Method 8
    // Returns a shallow copy of this ArrayList instance.
    public Object clone() { return linkedList.clone(); }

    // Method 9
    // Returns true if this list contains the specified
    // element.
    public boolean contains(Object o)
    {
        return linkedList.contains(o);
    }

    // Method 10
    // Returns an iterator over the elements in this
    // deque(reverse order)
    public Iterator<E> descendingIterator()
    {
        return linkedList.descendingIterator();
    }

    // Method 11
    // Retrieves, but does not remove, the head (first
    // element) of this list.
    public E element() { return linkedList.element(); }

    // Method 12
    // Returns the element at the specified position in this
    // list.
    public E get(int index)
    {
        return linkedList.get(index);
    }

    // Method 13
    // Returns the first element in this list.
    public E getFirst() { return linkedList.getFirst(); }

    // Method 14
    // Returns the last element in this list.
    public E getLast() { return linkedList.getLast(); }

    // Method 15
    // Returns the index of the first occurrence of the
    // specified element
    public int indexOf(Object o)
    {

        return linkedList.indexOf(o);
    }

    // Method 16
    // Returns true if this list contains no elements.
    public boolean isEmpty()
    {
        return linkedList.isEmpty();
    }

    // Method 17
    // Returns an iterator over the elements
    //  in this list in proper sequence.
    public Iterator<E> iterator()
    {
        return linkedList.iterator();
    }

    // Method 18
    public int lastIndexOf(Object o)
    {
        return linkedList.lastIndexOf(o);
    }

    // Method 19
    public ListIterator<E> listIterator()
    {
        return linkedList.listIterator();
    }

    // Method 20
    public ListIterator<E> listIterator(int index)
    {
        return linkedList.listIterator(index);
    }

    // Method 21
    // Adds the specified element as the tail (last element)
    // of this list.
    public boolean offer(E e)
    {
        return linkedList.offer(e);
    }

    // Method 22
    // Inserts the specified element at the front of this
    // list.
    public boolean offerFirst(E e)
    {
        return linkedList.offerFirst(e);
    }

    // Method 23
    // Inserts the specified element at the end of this
    // list.
    public boolean offerLast(E e)
    {
        return linkedList.offerLast(e);
    }

    // Method 24
    // Retrieves, but does not remove, the head (first
    // element) of this list.
    public E peek() { return linkedList.peek(); }

    // Method 25
    public E peekFirst() { return linkedList.peekFirst(); }

    // Method 26
    // Retrieves, but does not remove, the last element of
    // this list

    public E peekLast() { return linkedList.peekLast(); }

    // Method 27
    // Retrieves and removes the head (first element) of
    // this list.
    public E poll() { return linkedList.poll(); }

    // Method 28
    // Retrieves and removes the first element of this list,
    // or returns null
    public E pollFirst() { return linkedList.pollFirst(); }

    // Method 29
    // Retrieves and removes the last element of this list,
    // or returns null
    public E pollLast() { return linkedList.peekLast(); }

    // Method 30
    // Pops an element from the stack represented by this
    // list.
    public E pop() { return linkedList.pop(); }

    // Method 31
    // Pushes an element onto the stack represented by this
    // list.
    public void push(E e) { linkedList.push(e); }

    // Method 32
    // Removes the element at the specified position in this
    // list.
    public E remove(int index)
    {

        return linkedList.remove(index);
    }

    // Method 33
    // Removes the first occurrence of the specified element
    // from this list(if present)
    public boolean remove(Object o)
    {
        return linkedList.remove(o);
    }

    // Method 34
    public boolean removeAll(Collection<?> c)
    {

        return linkedList.removeAll(c);
    }

    // Method 35
    // Removes and returns the first element from this list.
    public E removeFirst()
    {

        return linkedList.removeFirst();
    }

    // Method 36
    // To remove th first occurences in this List
    public boolean removeFirstOccurence(Object o)
    {

        return linkedList.removeFirstOccurrence(o);
    }

    // Method 37
    // Removes and returns the last element from this list.
    public E removeLast()
    {

        return linkedList.removeLast();
    }

    // Method 38
    // Removes the last occurrence of the specified element
    // in this list
    public boolean removeLastOccurence(Object o)
    {

        return linkedList.removeLastOccurrence(o);
    }

    // Method 39
    // Retains only the elements in this list
    // contained in specific position
    public boolean retainAll(Collection<?> c)
    {

        return linkedList.removeAll(c);
    }

    // Method 40
    // Replaces the element at the specified position
    public E set(int index, E element)
    {
        return linkedList.set(index, element);
    }

    // Method 41
    // Returns the number of elements in this list.
    public int size() { return linkedList.size(); }

    // Method 42
    // Returns a view of the portion of this list
    public List<E> subList(int fromIndex, int toIndex)
    {

        return linkedList.subList(fromIndex, toIndex);
    }

    // Method 43
    // Returns an array containing all of the elements
    // in this list(proper sequence)
    public Object[] toArray()
    {

        return linkedList.toArray();
    }

    // Method 44
    // Returns an array containing all of the elements in
    // this list
    public <T> T[] toArray(T[] a)
    {
        return linkedList.toArray(a);
    }

    // Method 45
    // Main driver method
    public static void main(String... arg)
    {

        // Creating an object of above class
        // User-defined
        LinkedListImpl<Integer> linkedList
            = new LinkedListImpl<>();

        // Adding custom elements to above object

        // Custom input elements addition
        // using add() and addAll() methods
        linkedList.add(100);
        linkedList.add(20);
        linkedList.addFirst(101);
        linkedList.addLast(200);

        // Creating a Set class object of integer type
        Set<Integer> set = new HashSet<Integer>();

        // Custom input elements addition
        // using add() and addAll() methods
        set.add(101);
        set.add(30);
        set.add(32);
        linkedList.addAll(4, set);

        if (linkedList.contains(300))
            System.out.println(
                "the linked list contains 300");
        else
            System.out.println(
                "the linked list does not contain 300");

        System.out.println(
            "the elements in descending order is");
        Iterator<Integer> descendingitr
            = linkedList.descendingIterator();
        while (descendingitr.hasNext()) {
            System.out.print(descendingitr.next() + "\t");
        }
        System.out.println();

        System.out.println("the head of this list is "
                           + linkedList.element());

        System.out.println("the element at index 2 is "
                           + linkedList.get(2));

        System.out.println("the element first pos is  "
                           + linkedList.getFirst());

        System.out.println("the element at last pos is"
                           + linkedList.getLast());

        System.out.println("the index of element 200 is "
                           + linkedList.indexOf(200));
        System.out.println(
            "the last index of element 101 is "
            + linkedList.lastIndexOf(101));

        System.out.println("the elements of list are");
        Iterator<Integer> itr = linkedList.iterator();

        while (itr.hasNext()) {
            System.out.print(itr.next() + "\t");
        }
        System.out.println();

        linkedList.offer(45);
        linkedList.offerFirst(32);
        linkedList.offerLast(19);

        System.out.println("the head of the linkedlist is "
                           + linkedList.peek());

        System.out.println(
            "the first element of linkedList is "
            + linkedList.peekFirst());

        System.out.println(
            "the last element of linked List is "
            + linkedList.peekLast());

        System.out.println("the elements of list are");
        itr = linkedList.iterator();

        while (itr.hasNext()) {
            System.out.print(itr.next() + "\t");
        }
        System.out.println();

        System.out.println(
            "the first element of linkedList is (poll) "
            + linkedList.poll());

        System.out.println("the first element polled is "
                           + linkedList.pollFirst());

        System.out.println("the last element polled is "
                           + linkedList.pollLast());

        linkedList.push(36);

        System.out.println(
            "the element poped from linked List is "
            + linkedList.pop());

        System.out.println(
            "index 3 element removed from list "
            + linkedList.remove(3));

        System.out.println(
            "last occurence of 101 removed "
            + linkedList.removeLastOccurence(101));

        linkedList.clear();

        if (linkedList.isEmpty())
            System.out.println("the linkedList is empty");
        else
            System.out.println(
                "the linked list is not empty");
    }
}
```