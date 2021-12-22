# Java 中的 ConcurrentLinkedDeque offer()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-offer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-offer-method-in-java-with-examples/)

**T1。offer()方法**是 Java 中的一个内置方法，它将作为参数传递的指定元素插入到 deque 中。

**语法:**

```
public boolean offer(E elem)
```

**参数:**该方法接受一个参数 **elem** ，该参数指定了要插入到 deque 中的元素的种类。

**返回值:**如果元素成功添加到德格中，函数返回*真*，否则返回*假*。

**异常:**如果传递的参数为*空*，则函数抛出*空指针异常*。

下面的程序说明了**concurrentlinkedrequest . offer()**方法:

**程序 1** :

```
// Java Program to Demonstrate offer()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Insert an element using offer()
        if (cld.offer("GFG")) {

            // Displaying message
            System.out.println("Element Inserted");
        }
        else {

            // Displaying message
            System.out.println("Element not Inserted");
        }

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);
    }
}
```

**输出:**

```
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
Element Inserted
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks, GFG]

```

```
// Java Program to Demonstrate offer()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld
            = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        try {

            // Insert null element using offer()
            cld.offer(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
java.lang.NullPointerException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrentlinkedeque . html # offer-E-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#offer-E-)