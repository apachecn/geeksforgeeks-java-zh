# Java |实现迭代器和可迭代接口

> 原文:[https://www . geesforgeks . org/Java-implementing-iterator-and-iteratable-interface/](https://www.geeksforgeeks.org/java-implementing-iterator-and-iterable-interface/)

迭代器在 Java 的 Collection 框架中用于逐个检索元素。更多相关详情和介绍，请参见本[链接](https://www.geeksforgeeks.org/iterators-in-java/)。

**为什么需要实现 Iterable 接口？**

每个适当实现 Iterable 接口的类都可以用在增强的 For 循环(For-每个循环)中。设计定制数据结构时，需要实现迭代器接口。
例:

```
for(Item item: customDataStructure) {
    // do stuff
}

```

**如何实现 Iterable 接口？**

为了实现可迭代的数据结构，我们需要:

1.  在所述数据结构中实现可迭代接口及其方法
2.  创建一个迭代器类，实现迭代器接口和相应的方法。

我们可以将伪代码概括如下:

```
class CustomDataStructure implements Iterable<> {

    // code for data structure
    public Iterator<> iterator() {
        return new CustomIterator<>(this);
    }
}
class CustomIterator<> implements Iterator<> {

    // constructor
    CustomIterator<>(CustomDataStructure obj) {
        // initialize cursor
    }

    // Checks if the next element exists
    public boolean hasNext() {
    }

    // moves the cursor/iterator to next element
    public T next() {
    }

    // Used to remove an element. Implement only if needed
    public void remove() {
        // Default throws UnsupportedOperationException.
    }
}
```

**注意**:迭代器类也可以作为数据结构类的内部类来实现，因为它不会在其他地方使用。

1.  **next()和 hasNext()是如何工作的？**
    要实现迭代器，我们需要一个光标或指针来跟踪我们当前在哪个元素上。根据底层的数据结构，我们可以从一个元素前进到另一个元素。这是在 next()方法中完成的，该方法返回当前元素，光标前进到下一个元素。
    在推进指针之前，我们检查下一个元素是否存在。也就是说，我们可以将幕后代码图形化如下:

    ```
    While(iterator.hasNext()) { //if next element exists
        next(); // advance the pointer
    }

    ```

2.  **初始化光标**
    光标初始化完全取决于数据结构。例如，在链表中，我们将光标初始化为 head 元素。在数组列表中，我们将光标初始化为第 0 个元素。
    从实现的角度来看:
    *   如果迭代器类被实现为内部类，我们可以简单地使用“this”关键字(例如 cursor = customdatastructure . this . element)来访问所需的元素
    *   如果迭代器类被实现为一个单独的类，我们可以将数据结构的这个对象传递给迭代器类构造函数，如下例所示。

**下面的程序说明了 Iterable 接口的使用:**

下面给出了一个使用泛型的自定义链表。链表由节点对象组成，节点对象包含一个通用数据值和指向下一个节点的指针。该类提供了一些标准的“get”方法，如 getHead()和 getTail()，以及必要的 Iterator()函数，这些方法必须在实现 Iterable 接口时实现。

然后创建必要的自定义类“列表迭代器”，它将实现迭代器接口，同时还将实现 hasNext()和 Next()的功能。这两个函数构成了 Iterable 和 Iterator 接口的核心。

```
import java.util.Iterator;

// Custom Linked List class using Generics
class List<T> implements Iterable<T> {
    Node<T> head, tail;

    // add new Element at tail of the linked list in O(1)
    public void add(T data)
    {
        Node<T> node = new Node<>(data, null);
        if (head == null)
            tail = head = node;
        else {
            tail.setNext(node);
            tail = node;
        }
    }

    // return Head
    public Node<T> getHead()
    {
        return head;
    }

    // return Tail
    public Node<T> getTail()
    {
        return tail;
    }

    // return Iterator instance
    public Iterator<T> iterator()
    {
        return new ListIterator<T>(this);
    }
}

class ListIterator<T> implements Iterator<T> {
    Node<T> current;

    // initialize pointer to head of the list for iteration
    public ListIterator(List<T> list)
    {
        current = list.getHead();
    }

    // returns false if next element does not exist
    public boolean hasNext()
    {
        return current != null;
    }

    // return current data and update pointer
    public T next()
    {
        T data = current.getData();
        current = current.getNext();
        return data;
    }

    // implement if needed
    public void remove()
    {
        throw new UnsupportedOperationException();
    }
}

// Constituent Node of Linked List
class Node<T> {
    T data;
    Node<T> next;
    public Node(T data, Node<T> next)
    {
        this.data = data;
        this.next = next;
    }

    // Setter getter methods for Data and Next Pointer
    public void setData(T data)
    {
        this.data = data;
    }

    public void setNext(Node<T> next)
    {
        this.next = next;
    }

    public T getData()
    {
        return data;
    }

    public Node<T> getNext()
    {
        return next;
    }
}

// Driver class
class Main {
    public static void main(String[] args)
    {
        // Create Linked List
        List<String> myList = new List<>();

        // Add Elements
        myList.add("abc");
        myList.add("mno");
        myList.add("pqr");
        myList.add("xyz");

        // Iterate through the list using For Each Loop
        for (String string : myList)
            System.out.println(string);
    }
}
```

**Output:**

```
abc
mno
pqr
xyz

```