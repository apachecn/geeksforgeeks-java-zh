# concurrentlinkedeque 包含 Java 中的()方法，示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-contains-method-in-java-with-examples/)

**T1。contains()方法**是 Java 中的一个内置方法，它检查作为参数传递的指定元素是否存在于 deque 中。

**语法:**

```
public boolean contains(Object elem)
```

**参数:**该方法接受参数 **elem** ，该参数检查指定元素是否存在于目标中。

**返回值:**如果元素存在于德格中，函数返回*真*，否则返回*假*。

下面的程序说明了**concurrentlinkedequecontains()**方法:

**程序 1** :

```
// Java Program to Demonstrate contains()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Check if GFG is present using contains()
        if (cld.contains("GFG")) {

            // Displaying message
            System.out.println("GFG is present");
        }
        else {

            // Displaying message
            System.out.println("GFG is not present");
        }
    }
}
```

**输出:**

```
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
GFG is not present

```

**程序二:**

```
// Java Program to Demonstrate contains()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating an empty Deque
        ConcurrentLinkedDeque<String> cld = new ConcurrentLinkedDeque<String>();

        // Add elements into the Deque
        cld.add("Welcome");
        cld.add("To");
        cld.add("Geeks");
        cld.add("4");
        cld.add("Geeks");

        // Displaying the Deque
        System.out.println("ConcurrentLinkedDeque: "
                           + cld);

        // Check if Geeks is present using contains()
        if (cld.contains("Geeks")) {

            // Displaying message
            System.out.println("Geeks is present");
        }
        else {

            // Displaying message
            System.out.println("Geeks not present");
        }
    }
}
```

**输出:**

```
ConcurrentLinkedDeque: [Welcome, To, Geeks, 4, Geeks]
Geeks is present

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/concurrentlinkedeque . html # contains-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/util/concurrent/ConcurrentLinkedDeque.html#contains-java.lang.Object-)