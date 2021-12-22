# Java 中 LinkedBlockingQueue toArray()方法

> 原文:[https://www . geeksforgeeks . org/linkedblockingqueue-to array-method-in-Java/](https://www.geeksforgeeks.org/linkedblockingqueue-toarray-method-in-java/)

### toarray()

LinkedBlockingQueue 的 **toArray** 方法用于创建一个数组，该数组具有与该 LinkedBlockingQueue 相同的元素，并按适当的顺序排列。实际上，这个方法将 LinkedBlockingQueue 中的所有元素复制到一个新数组中。此方法充当数组和 LinkedBlockingQueue 之间的桥梁。

**语法:**

```java
public Object[] toArray()
```

**返回值:**这个方法返回一个包含 LinkedBlockingQueue 元素的数组。

下面的程序说明了 LinkedBlockingQueue 类的 toArray()方法:

**程序 1:**

## Java

```java
// Java Program Demonstrate toArray()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 50;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer> linkedQueue
            = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // Add element to LinkedBlockingQueue
        linkedQueue.add(2300);
        linkedQueue.add(1322);
        linkedQueue.add(8945);
        linkedQueue.add(6512);

        // print linkedQueue details
        System.out.println("Queue Contains "
                           + linkedQueue);

        // apply toArray() method on linkedQueue
        Object[] array = linkedQueue.toArray();

        // Print elements of array
        System.out.println("The array contains:");
        for (Object i : array) {
            System.out.print(i + "\t");
        }
    }
}
```

**输出:**

```java
Queue Contains [2300, 1322, 8945, 6512]
The array contains:
2300    1322    8945    6512
```

**程序二:**

## Java

```java
// Java Program Demonstrate toArray()
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {
    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 5;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add 5 elements to ArrayBlockingQueue
        linkedQueue.offer("User");
        linkedQueue.offer("Employee");
        linkedQueue.offer("Manager");
        linkedQueue.offer("Analyst");
        linkedQueue.offer("HR");

        // apply toArray() method on linkedQueue
        Object[] array = linkedQueue.toArray();

        // Print elements of array
        System.out.println("The array contains:");
        for (Object i : array) {
            System.out.print(i + " ");
        }
    }
}
```

**输出:**

```java
The array contains:
User Employee Manager Analyst HR
```

### toaarray(t[]a)

**LinkedBlockingQueue** 的 toArray(T[] a)方法用于以适当的顺序返回一个数组，该数组包含与该 LinkedBlockingQueue 相同的元素。此方法与 toArray()的区别仅在于一个条件。如果 LinkedBlockingQueue 的大小小于或等于传递的数组，则返回的数组的类型与参数中传递的数组相同。否则，将分配一个与指定数组类型相同的新数组，并且该数组的大小等于该队列的大小。此方法充当数组和集合之间的桥梁。

**语法:**

```java
public <T> T[] toArray(T[] a)
```

**参数:**该方法以一个**数组**为参数，如果队列足够大，队列的所有元素都将被复制到该数组中。否则，会为此分配一个相同运行时类型的新数组。

**返回值:**这个方法返回一个包含这个队列中所有元素的数组。

**异常**当传递的数组与 LinkedBlockingQueue 的元素类型不同时，该方法抛出以下异常:

*   **array storeexception:**。
*   **Null pointer exception:** If the passed array is empty.

下面的程序说明了 LinkedBlockingQueue 类的数组方法:

**程序 1**

## Java

```java
// Java program to demonstrate
// toArray(T[] a) method
// method of LinkedBlockingQueue

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 10;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String> linkedQueue
            = new LinkedBlockingQueue<String>(capacityOfQueue);

        // Add 5 elements to ArrayBlockingQueue
        linkedQueue.offer("Sonali");
        linkedQueue.offer("Sonam");
        linkedQueue.offer("Kajal");
        linkedQueue.offer("Komal");

        // Print queue
        System.out.println("Queue Contains : " + linkedQueue);

        // the array to pass in toArray()
        // array has size equal to size of linkedQueue
        String[] passArray = new String[linkedQueue.size()];

        // Calling toArray(T[] a) method
        Object[] array = linkedQueue.toArray(passArray);

        // Print elements of passed array
        System.out.println("\nThe array passed :");
        for (Object i : passArray) {
            System.out.print(i + "\t");
        }

        System.out.println();

        // Print elements of returned array
        System.out.println("\nThe array returned :");
        for (Object i : array) {
            System.out.print(i + "\t");
        }
    }
}
```

**输出**

```java
Queue Contains : [Sonali, Sonam, Kajal, Komal]

The array passed :
Sonali    Sonam    Kajal    Komal    

The array returned :
Sonali    Sonam    Kajal    Komal    
```

**程序 2:** 在 toArray()中传递不同于 LinkedBlockingQueue 包含的元素类型的数组。toArray()方法将因此引发异常 ArrayStoreException。

## Java

```java
// Java Program Demonstrate
// toArray()
// method Exceptions.

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<Integer>
            linkedQueue = new LinkedBlockingQueue<Integer>(capacityOfQueue);

        // add elements to queue
        linkedQueue.put(46541);
        linkedQueue.put(44648);
        linkedQueue.put(45654);

        // create a array of Strings
        String[] arr = {};

        // apply toArray method and Pass array of String
        // as parameter to toArray method
        try {
            // LinkedBlockingQueue has type Integer but we are passing
            // String Type array so toArray method will throw
            // Exception
            String[] array = linkedQueue.toArray(arr);

            // print elements of queue
            System.out.println("Items in Queue are " + array);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.ArrayStoreException: java.lang.Integer
```

**程序 3:** 在数组()中传递空数组。因此 toArray()方法将引发 NullPointerException。

## Java

```java
// Java program to demonstrate
// toArray() method Exceptions.

import java.util.concurrent.LinkedBlockingQueue;

public class GFG {

    public static void main(String[] args)
        throws InterruptedException
    {
        // define capacity of LinkedBlockingQueue
        int capacityOfQueue = 4;

        // create object of LinkedBlockingQueue
        LinkedBlockingQueue<String>
            linkedQueue = new LinkedBlockingQueue<String>(capacityOfQueue);

        // add elements to queue
        linkedQueue.put("aman");
        linkedQueue.put("khan");
        linkedQueue.put("Prakash");

        // create a array of Strings
        String[] arr = null;

        // apply toArray method and Pass array of String
        // as parameter to toArray method
        try {

            /// we are passing array with null values
            String[] array = linkedQueue.toArray(arr);

            // print elements of queue
            System.out.println("Items in Queue are " + array);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```java
Exception: java.lang.NullPointerException
```

**参考:**

*   [https://docs。甲骨文。com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue。html # to array–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#toArray--)
*   [https://docs。甲骨文。com/javase/8/docs/API/Java/util/concurrent/linkedblockingqueue。html # to array-T:A-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/LinkedBlockingQueue.html#toArray-T:A-)