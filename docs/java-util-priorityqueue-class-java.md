# Java 中的 Java.util.PriorityQueue 类

> 原文:[https://www . geesforgeks . org/Java-util-priorityqueue-class-Java/](https://www.geeksforgeeks.org/java-util-priorityqueue-class-java/)

它是基于优先级堆的优先级队列。

*   这个类中的元素是按自然顺序排列的，或者取决于我们在构建时使用的构造函数。
*   它不允许空指针。
*   如果依赖于自然排序，则不允许插入不可比较的对象。

**施工人员:**

*   **PriorityQueue():** 创建一个具有默认初始容量(11)的 PriorityQueue，它根据元素的自然顺序对其进行排序。
*   **优先级队列(集合 c):** 创建包含指定集合中元素的优先级队列。
*   **优先级队列(int initialCapacity)** :创建一个具有指定初始容量的优先级队列，该队列根据元素的自然顺序对其进行排序。
*   **优先级队列(int initialCapacity，Comparator comparator):** 创建具有指定初始容量的优先级队列，该队列根据指定的比较器对其元素进行排序。
*   **优先级队列(PriorityQueue c)** :创建包含指定优先级队列中元素的优先级队列。
*   **优先级队列(SortedSet c)** :创建包含指定排序集中元素的优先级队列。

**申报:**

```java
public class PriorityQueue
   extends AbstractQueue
   implements Serializable
```

**方法:**

1.  **添加(元素):** **将元素插入优先级队列。
    **语法:**

    ```java
    public boolean add(E e)
    Parameters  :
    element : the element we need to add.
    Return  :
    call return true.
    Exception : 
    -&gt ClassCastException 
    -&gt NullPointerException

    ```** 
2.  **comparator():****Java . util . priorityqueue . comparator()**对队列中的元素进行排序。
    **语法:**

    ```java
    public Comparator comparator()
    Parameters  :
    -------
    Return  :
    orders the queue or return null, if it is naturally ordered 
    Exception : 
    ----------

    ```

3.  **contains(Object obj):****Java . util . priorityqueue . contains(obj)**如果优先级队列包含元素“obj”，则返回 true。
    **语法:**

    ```java
    public boolean contains(Object obj)
    Parameters  :
    obj : object to be checked
    Return  :
    true - if the object is present else, return false
    Exception : 

    ```

4.  **迭代器():****Java . util . priorityqueue . iterator()**迭代队列元素。
    **语法:**

    ```java
    public Iterator iterator()
    Parameters  :
    -------
    Return  :
    calls iterator over the elements in the queue.
    Exception : 
    --------

    ```

5.  **offer(元素):****Java . util . priorityqueue . offer()**需要在给定的优先级队列中插入特定的元素。
    **语法:**

    ```java
    public boolean offer(E element)
    Parameters  :
    element : specific element to  be entered.
    Return  :
    call return true.
    Exception : 
    -&gt ClassCastException 
    -&gt NullPointerException

    ```

6.  **peek():****Java . util . priorityqueue . peek()**标识队列的头元素。
    **语法:**

    ```java
    public E peek()    
    Parameters  :
    -------
    Return  :
    calls if head exists, else null
    Exception : 
    ------

    ```

7.  **poll():****Java . util . priorityqueue . poll()**识别头部，然后将其移除。
    **语法:**

    ```java
    public E poll()    
    Parameters  :
    ---
    Return  :
    calls if head exists, else null
    Exception : 
    ------

    ```

8.  **移除(对象对象):** **从队列中移除特定对象。
    **语法:**

    ```java
    public boolean remove(Object obj)
    Parameters  :
    obj : object to be removed
    Return  :
    true - if obj is removed
    Exception : 
    ------

    ```** 
9.  **size():****Java . util . priorityqueue . size()**返回优先级队列中元素的大小。
    **语法:**

    ```java
    public int size()
    Parameters  :
    ----
    Return  :
    no. of elements
    Exception : 
    ---------

    ```

10.  **to array():****Java . util . PriorityQueue . to array()**返回一个包含 PriorityQueue 元素的数组。
    **语法:**

    ```java
    public Object[] toArray()
    Parameters  :
    ------
    Return  :
    returns an array containing all the elements of PriorityQueue.
    Exception : 
    --------

    ```

11.  **toArray(T[]数组):****Java . util . priorityqueue . to array(T[]a)**返回具有优先级队列元素的数组。
    **语法:**

    ```java
    public  T[] toArray(T[] array)
    Parameters  :
    array  : the array to which are to be sorted. 
    Return  :
    call an array containing all the elements of the array. 
    Exception : 
    -> ArrayStoreException
    -> NullPointerException

    ```

12.  **clear() :** **java.util.PriorityQueue.clear()** clears all the elements of the PriorityQueue.
    **Syntax :**

    ```java
    public void clear()        
    Parameters  :
    ---
    Return  :
    ------
    Exception : 
    ------

    ```

    ```java
    // Java Program illustrating the methods
    // of java.utl.priorityQueue class

    // add(), comparator(), conatins(), iterator(), offer()
    // peek(), poll(), toArray(), size(), toArray(t[] g1),
    // remove(), clear()

    import java.util.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            // Creating a Priority Queue :
            PriorityQueue <Integer> geek = new PriorityQueue <Integer> ();

            for(int i=2; i<=20; i=i+2)
            {
                // Use of add() :
                geek.add(new Integer (i));
            }

            System.out.println("geek PriorityQueue : " + geek);

            // Use of comparator() 
            // No ordering is required here as it is naturally ordered.
            Comparator geek_comp = geek.comparator();
            System.out.println("geek PriorityQueue : " + geek_comp);

            // Use of contains() 
            boolean check = geek.contains(6);
            System.out.println("Use of contains() : " + check);

            // Use of iterator() 
            Iterator g_iterator = geek.iterator();

            System.out.print("Iterator values : ");
            while(g_iterator.hasNext())
            {
                System.out.print(g_iterator.next() + " ");
            }
            System.out.println("");

            // Use of offer() 
            geek.offer(3050);
            System.out.println("geek PriorityQueue : " + geek);

            // Use of peek() 
            System.out.println("Head of PriorityQueue via peek : " + geek.peek());

            //Use of poll() 
            int h = geek.poll();
            System.out.println("\nHead of PriorityQueue via poll : " + h);
            System.out.println("geek PriorityQueue bcz of poll() : " + geek);

            // Use of remove()
            boolean r = geek.remove(8);
            System.out.println("\nCan remove : " + r);
            System.out.println("geek PriorityQueue bcz of remove() : " + geek);

            // use of size() 
            System.out.println("\nSize of PriorityQueue : " + geek.size());

            // Use of toArray() 
            Object[] g = geek.toArray();
            System.out.print ( "Array from PriorityQueue : ");

            for ( int i = 0; i<g.length; i++ )
            {
                System.out.print (g[i].toString() + " ") ;
            }

            System.out.println("\n");

            // Use of toArray(t[] g1) :
            Integer[] g2 = new Integer[5];
            Integer[] g1 = geek.toArray(g2);
            System.out.print ( "Array from PriorityQueue of size 5 : ");

            for ( int i = 0; i<g1.length; i++ )
            {
                System.out.print (g1[i].toString() + " ") ;
            }

            System.out.println("\n");

            // Use of clear() 
            geek.clear();
            System.out.println("PriorityQueue after clear() : " + geek);

        }
    }
    ```

    **输出:**

    ```java
    geek PriorityQueue : [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]
    geek PriorityQueue : null
    Use of contains() : true
    Iterator values : 2 4 6 8 10 12 14 16 18 20 
    geek PriorityQueue : [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 3050]
    Head of PriorityQueue via peek : 2

    Head of PriorityQueue via poll : 2
    geek PriorityQueue bcz of poll() : [4, 8, 6, 16, 10, 12, 14, 3050, 18, 20]

    Can remove : true
    geek PriorityQueue bcz of remove() : [4, 10, 6, 16, 20, 12, 14, 3050, 18]

    Size of PriorityQueue : 9
    Array from PriorityQueue : 4 10 6 16 20 12 14 3050 18 

    Array from PriorityQueue of size 5 : 4 10 6 16 20 12 14 3050 18 

    PriorityQueue after clear() : []
    ```

本文由 <font color="green">**Mohit Gupta_OMG 供稿🙂**</font> 。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。