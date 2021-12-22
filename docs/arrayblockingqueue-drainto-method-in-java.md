# Java 中的 ArrayBlockingQueue drainTo()方法

> 原文:[https://www . geeksforgeeks . org/arrayblockingqueue-drain to-method-in-Java/](https://www.geeksforgeeks.org/arrayblockingqueue-drainto-method-in-java/)

[**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)是有界的，阻塞队列存储由数组支持的内部元素。

*   [**ArrayBlockingQueue**](https://www.geeksforgeeks.org/arrayblockingqueue-class-in-java/)类是 Java Collections 框架的成员。
*   有界意味着它将有一个固定的大小，你不能存储的元素数量超过队列的容量。
*   队列还遵循先进先出规则来存储和移除队列中的元素。
*   如果你试图把一个元素放到一个满的队列中，或者从一个空的队列中取出一个元素，那么这个队列就会阻塞你。

**drainTo(** ***集合 c*** **)** 方法**从该队列中移除所有可用元素，并将它们添加到给定集合**中。元素的数量也可以是固定的，通过提供元素的数量“n”作为该方法的第二个参数，需要排出这些元素。

根据传递给它的参数，有两种类型的 drainTo 方法:

1.drainTo()方法用于将所有元素转移到集合中。消耗操作比使用循环重复轮询这个队列更有效。当试图将元素添加到*集合 c* 时，也有可能遇到失败，因此当抛出相关异常时，失败元素可能既不出现在两个集合中，也不出现在两个集合中。如果您试图将队列排到自身，将引发 IllegalArgumentException。如果在操作过程中修改了指定的集合，则此操作的行为未定义。所以为了使用这样的方法，我们需要注意这种情况，这样我们就可以克服异常。

**语法**

```java
public int drainTo(*Collection c*)
```

**参数:**该方法接受一个参数 *c* ，该参数是指要转移元素的集合

**返回值:**该方法返回排出的元素数量。

**异常:**该方法可能会抛出三种类型的异常:

*   *不支持操作异常*–如果指定集合不支持添加元素
*   *class castexception*–如果该队列的某个元素的类阻止它被添加到指定的集合中
*   *空指针异常*–如果指定的集合为空
*   **IllegalArgumentException**–如果指定的集合是这个队列，或者这个队列的某个元素的某些属性阻止它被添加到指定的集合中

下面的程序说明了 ArrayBlockingQueue 的 drainTo( *Collection c* )方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to demonstrate drainTo(Collection c)

import java.util.ArrayList;
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 10;

        // Create object of  ArrayBlockingQueue
        ArrayBlockingQueue queue = new
              ArrayBlockingQueue(capacity);

        // Add elements to ArrayBlockingQueue
        queue.add(23);
        queue.add(32);
        queue.add(45);
        queue.add(12);
        queue.add(27);
        queue.add(67);

        // Print queue before drainTo operation
        System.out.println("Before drainTo Operation");
        System.out.println("queue = " + queue);

        // Create Collection object to
        // tranfer elements
        ArrayList list = new
                           ArrayList();

        // Call drainTo method of queue
        // and pass collection as parameter.
        queue.drainTo(list);

        // Print queue before drainTo operation
        System.out.println("After drainTo Operation");
        System.out.println("queue = " + queue);
        System.out.println("collection = " + list);
    }
}
```

**Output:**

```java
Before drainTo Operation
queue = [23, 32, 45, 12, 27, 67]
After drainTo Operation
queue = []
collection = [23, 32, 45, 12, 27, 67]
```

2.**drain to(*****Collection c，int maxElements*** **)** 方法用于将固定数量的元素转移到集合中。传输指定数组的元素号后，阻塞队列只包含那些没有传输到集合的元素。该功能与上述功能相同，但有一些局限性。

**语法:**

```java
public int drainTo(*Collection c, int maxElements*)
```

**参数:**该方法接受两个参数:

*   *c*–这是指转移元素的集合。
*   maxElements–这是整数类型，指的是要传输到集合中的元素的最大数量。

**返回值:**
耗尽的元素数量。

**异常:**

*   *不支持操作异常*–如果指定集合不支持添加元素
*   *class castexception*–如果该队列的某个元素的类阻止它被添加到指定的集合中
*   *空指针异常*–如果指定的集合为空
*   *IllegalArgumentException*–如果指定的集合是这个队列，或者这个队列的某个元素的某些属性阻止它被添加到指定的集合中

下面的程序说明了 ArrayBlockingQueue 的 drainTo(Collection c，int maxElements)方法的工作原理。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program Demonstrate drainTo(Collection c, int maxElements)
// method of ArrayBlockingQueue

import java.util.ArrayList;
import java.util.concurrent.ArrayBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // Define capacity of ArrayBlockingQueue
        int capacity = 10;

        // Create object of  ArrayBlockingQueue
        ArrayBlockingQueue queue = new
               ArrayBlockingQueue(capacity);

        // Add elements to ArrayBlockingQueue
        queue.add("aman");
        queue.add("sudhir");
        queue.add("harsh");
        queue.add("rahul");
        queue.add("raunak");

        // Print queue before drainTo operation
        System.out.println("Before drainTo Operation");
        System.out.println("queue = " + queue);

        // Transfer elements from ArrayBlockingQueue;
        ArrayList list = new ArrayList();

        // Define no of elements to be  tranfered
        int maxElements = 3;

        // Call drainTo method of queue and pass
        // the collection as parameter.
        queue.drainTo(list, maxElements);

        // Print queue before drainTo operation
        System.out.println("After drainTo Operation");
        System.out.println("queue = " + queue);
        System.out.println("collection = " + list);
    }
}
```

**Output:**

```java
Before drainTo Operation
queue = [aman, sudhir, harsh, rahul, raunak]
After drainTo Operation
queue = [rahul, raunak]
collection = [aman, sudhir, harsh]
```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/arrayblockingqueue . html # drain to(Java . util . collection)T4】