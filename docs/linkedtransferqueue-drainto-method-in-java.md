# Java 中的 LinkedTransferQueue drainTo()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-drain to-method-in-Java/](https://www.geeksforgeeks.org/linkedtransferqueue-drainto-method-in-java/)

### 排水(集合 c)

**java . util . concurrent . linkedtransferqueue**类的 **drainTo(Collection c)** 方法是 Java 中的一个内置函数，它删除这个队列中存在的所有元素，并将它们添加到提供的集合中。这是比重复轮询这个队列更有效的方法。

尝试从队列中向集合 c 添加元素时也可能遇到失败，并且由于该失败，当引发关联的异常时，元素会在两个集合之间分布。如果一个队列试图将 threatto()排入队列本身，那么将会抛出 **IllegalArgumentException** 。如果在操作过程中修改了指定的集合，则此操作的行为未定义。因此，为了使用这样的方法，需要注意这种类型的情况来克服异常。

**语法:**

```java
public int drainTo(Collection c)
```

**参数:**该函数接受一个强制参数 **c** ，该参数是元素要转移到的集合。

**返回值:**该函数返回从队列中排入集合的元素数量。

**异常:**该方法抛出以下异常:

*   **空指针异常**–如果集合为空
*   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

下面的程序说明了 Java . util . concurrent . LinkedTransferqueue . DrainTo()方法的使用:

**程序 1:** 将队列中的所有元素排到指定集合的程序。

```java
// Java Program Demonstrate drainTo()
// method of LinkedTransferQueue

import java.util.*;
import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the List
        List<Integer> list = new ArrayList<Integer>();

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // Adding elements to this queue
        for (int i = 10; i <= 15; i++)
            queue.add(i);

        // Printing the elements of the queue
        System.out.println("Elements in the queue = "
                           + queue);

        // drainTo() method removes all available elements
        // from this queue and adds them to the list
        queue.drainTo(list);

        // Printing the elements of the queue after drainTo()
        System.out.println("Elements left in the queue :"
                           + queue);

        // Printing the elements of the list
        System.out.println("Elements drained in the list :"
                           + list);
    }
}
```

**Output:**

```java
Elements in the queue = [10, 11, 12, 13, 14, 15]
Elements left in the queue :[]
Elements drained in the list :[10, 11, 12, 13, 14, 15]

```

**程序 2:** 在 drainTo()中显示空指针异常的程序。

```java
// Java Program Demonstrate drainTo()
// method of LinkedTransferQueue

import java.util.ArrayList;
import java.util.concurrent.LinkedTransferQueue;

class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Initializing the queue
        LinkedTransferQueue<Integer>
            queue = new LinkedTransferQueue<Integer>();

        // add elements to queue
        queue.put(10);
        queue.put(20);
        queue.put(30);

        // create a collection with null
        ArrayList<Integer> add = null;

        // try to drain null queue to collection
        try {
            // this will throw exception
            // as the add list is null
            queue.drainTo(add);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```

### 排水(c 集合，int maxElements)

**java . util . concurrent . linkedtransferqueue**的 **drainTo(Collection c，int maxElements)** 方法是 Java 中的内置函数，用于将 drainTo()中作为整数传递的固定数量的元素传递给集合，集合也作为参数传递给方法。传输元素后，LinkedTransferQueue 只有那些没有传输到集合的元素。该函数与上面的函数相同，只是在传递固定数量的元素时有一些限制。

**语法:**

```java
public int drainTo(Collection c,
          int maxElements)
```

**参数:**该方法接受两个参数:

*   **c**–表示从 LinkedTransferQueue 传输元素的集合。
*   **maxElements**– This is of integer type and refers to the maximum number of elements to be transferred to the collection.

    **返回值:**该函数返回从队列中排入集合的元素数量。

    **异常:**该方法抛出以下异常:

    *   **空指针异常**–如果集合为空
    *   **IllegalArgumentException**–如果方法的参数阻止它被添加到指定的集合中

    **程序 1:** 将队列中最多给定数量的可用元素排入指定集合的程序。

    ```java
    // Java Program Demonstrate drainTo()
    // method of LinkedTransferQueue

    import java.util.ArrayList;
    import java.util.List;
    import java.util.concurrent.LinkedTransferQueue;

    class GFG {
        public static void main(String[] args)
        {

            // Initializing the List
            List<Integer> list = new ArrayList<Integer>();

            // Initializing the queue
            LinkedTransferQueue<Integer>
                queue = new LinkedTransferQueue<Integer>();

            // Adding elements to this queue
            for (int i = 1; i <= 10; i++)
                queue.add(i);

            // Printing the elements of the queue
            System.out.println("Elements in the queue = "
                               + queue);

            // drainTo() method removes at most
            // the given number of available elements
            // from this queue and adds them to the list.
            queue.drainTo(list, 5);

            // Printing the elements of the queue after drainTo()
            System.out.println("Elements left in the queue :"
                               + queue);

            // Printing the elements of the list
            System.out.println("Elements drained in the list :"
                               + list);
        }
    }
    ```

    **Output:**

    ```java
    Elements in the queue = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    Elements left in the queue :[6, 7, 8, 9, 10]
    Elements drained in the list :[1, 2, 3, 4, 5]

    ```

    **程序 2:** 在 drainTo()中显示空指针异常的程序。

    ```java
    // Java Program Demonstrate drainTo()
    // method of LinkedTransferQueue

    import java.util.ArrayList;
    import java.util.concurrent.LinkedTransferQueue;

    class GFG {
        public static void main(String[] args)
            throws InterruptedException
        {

            // Initializing the queue
            LinkedTransferQueue<Integer>
                queue = new LinkedTransferQueue<Integer>();

            // add elements to queue
            queue.put(10);
            queue.put(20);
            queue.put(30);

            // create a collection with null
            ArrayList<Integer> add = null;

            // try to drain null queue to collection
            try {
                // this will throw exception
                // as the add list is null
                queue.drainTo(add, 2);
            }
            catch (Exception e) {
                System.out.println("Exception: " + e);
            }
        }
    }
    ```

    **Output:**

    ```java
    Exception: java.lang.NullPointerException

    ```

    **参考:**

    *   [https://docs . Oracle . com/javae/7/docs/API/Java/util/concurrent/linked transfer queue . html # drank(Java . util . collection)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#drainTo(java.util.Collection))
    *   [https://docs . Oracle . com/javae/7/docs/API/Java/util/concurrent/linked transfer queue . html # draento(Java . util . collection，%20int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#drainTo(java.util.Collection, %20int))