# 实现矢量应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-vector-api/](https://www.geeksforgeeks.org/java-program-to-implement-vector-api/)

[Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 是一种线性数据结构，也称为可生长数组。插入或删除元素时，矢量能够自动调整自身大小。在向量中，数据被插入到末尾。它们非常类似于[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)，但是 Vector 是同步的，并且有一些收集框架不包含的遗留方法。

**申报**

> 公共类向量<e>扩展抽象列表<e>实现列表<e>，随机访问，可克隆，可序列化</e></e></e>

这里 **E** 是元素的类型。

向量 API 实现[可序列化](https://www.geeksforgeeks.org/serializable-interface-in-java/)、[可克隆](https://www.geeksforgeeks.org/cloneable-interface-in-java/)、[可迭代<E>T5】、](https://www.geeksforgeeks.org/iterable-interface-in-java/)[集合<E>T7】、](https://www.geeksforgeeks.org/collection-interface-in-java-with-examples/)[列表<E>T9】、**随机访问**](https://www.geeksforgeeks.org/list-interface-java-examples/)

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement Vector API
import java.util.*;

public class VectorImplement<E> {
    private Vector<E> vector;

    // Constructor to create an empty vector(internal array
    // has size 10)
    public VectorImplement() { vector = new Vector<E>(); }

    // Constructor to create a vector with it's element
    // as specified in given collection
    public VectorImplement(Collection<? extends E> c)
    {
        vector = new Vector<E>(c);
    }

    // Constructor to create an empty vector with the given
    // initial capacity .
    public VectorImplement(int initialCapacity)
    {
        vector = new Vector<E>(initialCapacity);
    }

    // Constructor to create an empty vector with the given
    // initial capacity and capacity increment.
    public VectorImplement(int initialCapacity,
                           int capacityIncrement)
    {
        vector = new Vector<E>(initialCapacity,
                               capacityIncrement);
    }

    // method to append a specified element to the Vector.
    public boolean add(E e) { return vector.add(e); }

    // method to insert a given element at the specified
    // position in the Vector.
    public void add(int index, E element)
    {
        vector.add(index, element);
    }

    // method to append all of the elements to the Vector.
    public boolean addAll(Collection<? extends E> c)
    {
        return vector.addAll(c);
    }

    // method to insert all of the elements of a Collection
    // at a specified position.
    public boolean addAll(int index,
                          Collection<? extends E> c)
    {
        return vector.addAll(index, c);
    }

    // method to append specific element to the vector.Size
    // of vector increases by 1.
    public void addElement(E obj)
    {
        vector.addElement(obj);
    }

    // method to returns the current capacity of vector.
    public int capacity() { return vector.capacity(); }

    // method to remove all of the elements of the Vector.
    public void clear() { vector.clear(); }

    // method to return a clone of this vector.
    public Object clone() { return vector.clone(); }

    // method to check vector contains a specific element.
    public boolean contains(Object o)
    {
        return vector.contains(o);
    }

    // method to return true if Vector contains all of the
    // elements in the specified Collection.
    public boolean containsAll(Collection<?> c)
    {
        return vector.containsAll(c);
    }

    // method to Copy the elements of this vector into a
    // specific array.
    public void copyInto(Object[] anArray)
    {
        vector.copyInto(anArray);
    }

    // method to return the element at the specified index.
    // **/
    public E elementAt(int index)
    {
        return vector.elementAt(index);
    }

    // method to return an enumeration of the element of the
    // vector. **/
    public Enumeration<E> elements()
    {
        return vector.elements();
    }

    // method to increase the capacity of this vector to a
    // minimum capacity.
    public void ensureCapacity(int minCapacity)
    {
        vector.ensureCapacity(minCapacity);
    }

    // method to compare a specified elements with this
    // Vector for equality.
    public boolean equals(Object o)
    {
        return vector.equals(o);
    }

    // method to return the first element of the vector
    public E firstElement()
    {
        return vector.firstElement();
    }

    // method to return the element at the specified index
    // in the Vector.
    public E get(int index) { return vector.get(index); }

    // method to return the hash code value for the Vector
    public int hashCode() { return vector.hashCode(); }

    // method to return the index of the first occurrence of
    // the specified element in
    // this vector, or -1 if the vector does not contain the
    // specified element.
    public int indexOf(Object obj)
    {
        return vector.indexOf(obj);
    }

    // method to return the index of the last occurrence of
    // a specific element in this
    // vector, searching backwards from index, or returns
    // -1 if the element is not found.
    public int indexOf(Object obj, int index)
    {
        return vector.indexOf(obj, index);
    }

    // method to insert a specified object at a specified
    // index
    public void insertElementAt(E obj, int index)
    {
        vector.insertElementAt(obj, index);
    }

    // method to test if the vector has no elements.
    public boolean isEmpty() { return vector.isEmpty(); }

    // method to return an iterator over the elements in
    // this list in proper sequence.
    public Iterator<E> iterator()
    {
        return vector.iterator();
    }

    // method to return the last element of the vector.
    public E lastElement() { return vector.lastElement(); }

    // method to return the index of the last occurrence of
    // the specific element in the vector, else return -1 if
    // the vector does not contain the element.
    public int lastIndexOf(Object o)
    {
        return vector.lastIndexOf(o);
    }

    // method to return the index of the last occurrence of
    // a specific element in the vector, searching backwards
    // from index, else returns -1 if the element is not
    // found.
    public int lastIndexOf(Object o, int index)
    {
        return vector.lastIndexOf(o, index);
    }

    // method to return a list iterator over the elements in
    // this list.
    public ListIterator<E> listIterator()
    {
        return vector.listIterator();
    }

    // method to return a list iterator over the elements in
    // this list starting at the specific position in the
    // list.
    public ListIterator<E> listIterator(int index)
    {
        return vector.listIterator(index);
    }

    // method to remove the element at the specified
    // position in the Vector.
    public E remove(int index)
    {
        return vector.remove(index);
    }

    // method to remove the first occurrence of a specific
    // element in the Vector.
    public boolean remove(Object o)
    {
        return vector.remove(o);
    }

    // method to remove from this Vector all of its elements
    // that are contained in the specified Collection.
    public boolean removeAll(Collection<?> c)
    {
        return vector.removeAll(c);
    }

    // removes all elements from the vector and set size=0.
    public void removeAllElements()
    {
        vector.removeAllElements();
    }

    // method to remove the first occurrence of the element
    // from the vector. **/
    public boolean removeElement(Object obj)
    {
        return vector.removeElement(obj);
    }

    // method to retain only the elements in  Vector that
    // are contained in specified Collection.
    public boolean retainAll(Collection<?> c)
    {
        return vector.removeAll(c);
    }

    // method to replace the element at the specified
    // position in the Vector with another specified element.
    public E set(int index, E element)
    {
        return vector.set(index, element);
    }

    // method to set the element at the specified index of
    // vector
    public void setElementAt(E obj, int index)
    {
        vector.setElementAt(obj, index);
    }

    // method to set the size of vector
    public void setSize(int newSize)
    {
        vector.setSize(newSize);
    }

    // method to returns size of vector
    public int size() { return vector.size(); }

    // method to return a sub-vector between
    // fromIndex(inclusive) and toIndex(exclusive).
    public List<E> subList(int fromIndex, int toIndex)
    {
        return vector.subList(fromIndex, toIndex);
    }

    // method to trim the capacity to the vector current
    // size
    public void trimToSize() { vector.trimToSize(); }

    public static void main(String[] arg)
    {
        // creating a object of VectorImplement class
        VectorImplement<String> vector
            = new VectorImplement<String>();

        // adding elements to vector
        vector.add("one");
        vector.add("three");
        vector.add("five");
        vector.add("ten");
        vector.addElement("seven");
        vector.addElement("six");

        // printing the capacity of vector
        System.out.println("The capacity of the vector is "
                           + vector.capacity());

        // printing the elements of vector
        System.out.println("Elements of vector is ");
        Enumeration<String> elements = vector.elements();
        while (elements.hasMoreElements()) {
            System.out.print(elements.nextElement() + "\t");
        }
        System.out.println();

        // checking if vector contains a specific element
        System.out.println(
            "checking if vector contains element - ten");
        if (vector.contains("ten") == true) {
            System.out.print(
                "The vector contains element ten");
        }
        else {
            System.out.print(
                "The vector does not contains element ten");
        }
        System.out.println();

        // printing first element of vector
        System.out.println("The first element of vector is "
                           + vector.firstElement());

        // printing first element of vector
        System.out.println("The last element of vector is  "
                           + vector.lastElement());

        // removing an element from the vector
        System.out.println("Removing element ten"
                           + vector.remove("ten"));

        // printing vector size
        System.out.println("The size of the vector is "
                           + vector.size());
    }
}
```

**Output**

```
The capacity of the vector is 10
Elements of vector is 
one    three    five    ten    seven    six    
checking if vector contains element - ten
The vector contains element ten
The first element of vector is one
The last element of vector is  six
Removing element tentrue
The size of the vector is 5
```