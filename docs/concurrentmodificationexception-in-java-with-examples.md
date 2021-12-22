# Java 中的 ConcurrentModificationException，示例

> 原文:[https://www . geeksforgeeks . org/concurrentmodificationexception-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentmodificationexception-in-java-with-examples/)

<u>**并发修改多线程环境中的异常**</u>

在 **[多线程环境](https://www.geeksforgeeks.org/multithreading-in-java/)** 中，如果在资源检测期间，任何方法发现该对象存在不允许的并发修改，则可能会引发该并发修改异常。

1.  If this exception is detected, the result of iteration is undefined.
2.  Generally speaking, some iterator implementations choose to throw this exception, which is called **[Fail fast iterator](https://www.geeksforgeeks.org/fail-fast-fail-safe-iterators-java/) .**

**例如:**如果我们试图使用一个线程修改代码中的任何集合，但是另一个线程已经在使用该集合，那么这是不允许的。

<u>**并发修改单线程环境中的异常**</u>

因为，不能保证每当引发这个异常时，一个对象已经被某个不同的线程并发修改，这个异常也会在**单线程环境**中抛出。

如果我们在违反约定的对象上调用一系列方法，那么该对象将抛出 ConcurrentModificationException。

**例如:**如果在迭代集合时，我们直接尝试修改该集合，那么给定的[快速失败迭代器](https://www.geeksforgeeks.org/fail-fast-fail-safe-iterators-java/)将抛出这个 ConcurrentModificationException。

<u>**示例:**</u> 在下面的代码中，实现了一个 ArrayList。然后向其添加很少的值，并在遍历时对其进行很少的修改，

```
// Java program to show
// ConcurrentModificationException

import java.util.Iterator;
import java.util.ArrayList;

public class modificationError {
    public static void main(String args[])
    {

        // Creating an object of ArrayList Object
        ArrayList<String> arr
            = new ArrayList<String>();

        arr.add("One");
        arr.add("Two");
        arr.add("Three");
        arr.add("Four");

        try {
            // Printing the elements
            System.out.println(
                "ArrayList: ");
            Iterator<String> iter
                = arr.iterator();

            while (iter.hasNext()) {

                System.out.print(iter.next()
                                 + ", ");

                // ConcurrentModificationException
                // is raised here as an element
                // is added during the iteration
                System.out.println(
                    "\n\nTrying to add"
                    + " an element in "
                    + "between iteration\n");
                arr.add("Five");
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
ArrayList: 
One, 

Trying to add an element in between iteration

java.util.ConcurrentModificationException

```

<u>**如何避免 ConcurrentModificationException？**T3】</u>

为了避免这个异常，

*   Simply put, we can modify it after the iteration is completed, or
*   Concept or method of realizing [synchronization block](https://www.geeksforgeeks.org/method-block-synchronization-java/)

**示例:**让我们看看如何通过简单地更改修改的地方来解决这个异常。

```
// Java program to show
// ConcurrentModificationException

import java.util.Iterator;
import java.util.ArrayList;

public class modificationError {
    public static void main(String args[])
    {

        // Creating an object of ArrayList Object
        ArrayList<String> arr
            = new ArrayList<String>();

        arr.add("One");
        arr.add("Two");
        arr.add("Three");
        arr.add("Four");

        try {
            // Printing the elements
            System.out.println(
                "ArrayList: ");
            Iterator<String> iter
                = arr.iterator();

            while (iter.hasNext()) {
                System.out.print(iter.next()
                                 + ", ");
            }

            // No exception is raised as
            // a modification is done
            // after the iteration
            System.out.println(
                "\n\nTrying to add"
                + " an element in "
                + "between iteration: "
                + arr.add("Five"));

            // Printing the elements
            System.out.println(
                "\nUpdated ArrayList: ");
            iter = arr.iterator();

            while (iter.hasNext()) {
                System.out.print(iter.next()
                                 + ", ");
            }
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
ArrayList: 
One, Two, Three, Four, 

Trying to add an element in between iteration: true

Updated ArrayList: 
One, Two, Three, Four, Five,

```

从输出中可以清楚地看到，只要对代码进行最小的更改，就可以消除 ConcurrentModificationException。