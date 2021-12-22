# Java 中的 ConcurrentLinkedDeque push()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentlinkedeque-push-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentlinkeddeque-push-method-in-java-with-examples/)

**[concurrentlinkedeque](https://www.geeksforgeeks.org/concurrentlinkeddeque-in-java-with-examples/)**类的 **push()** 方法是 Java 中的一个内置函数，它将一个元素推送到这个 dequee 所表示的堆栈上(换句话说，在这个 dequee 的头部)，如果可以立即这样做而不违反容量限制，则返回 true，如果当前没有可用空间，则抛出 IllegalStateException。

**语法:**

```
public void push(E e)

Here, E is the type of element maintained 
by this collection class.

```

**参数:**该方法只接受一个参数**元素**，该元素将被添加到并发链接请求的头部。

**返回值:**函数没有返回值。

**异常:**方法会抛出以下异常。

*   **illegalstatexception:**如果此时由于容量限制无法添加元素。
*   **ClassCastException:** 如果指定元素的类阻止它被添加到这个 deque。
*   **NullPointRexception:**如果指定的元素为空，并且这个 deque 不允许空元素。
*   **IllegalArgumentException:**如果指定元素的某些属性阻止它被添加到这个 deque。

下面的程序说明了 ConcurrentLinkedDeque.push()方法:

**程序 1:** 该程序涉及字符类型的并发链接请求。

```
// Java program to demonstrate push()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD
            = new ConcurrentLinkedDeque<String>();

        // Use push() method to add elements
        CLD.push("Welcome");
        CLD.push("To");
        CLD.push("Geeks");
        CLD.push("For");
        CLD.push("Geeks");

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: [Geeks, For, Geeks, To, Welcome]

```

**程序 2:** 显示空指针异常。

```
// Java program to demonstrate push()
// method of ConcurrentLinkedDeque

import java.util.concurrent.*;

public class GFG {
    public static void main(String[] args)
    {
        // Creating an empty ConcurrentLinkedDeque
        ConcurrentLinkedDeque<String> CLD
            = new ConcurrentLinkedDeque<String>();

        // Displaying the ConcurrentLinkedDeque
        System.out.println("ConcurrentLinkedDeque: "
                           + CLD);

        try {

            System.out.println("Trying to add "
                               + "null in ConcurrentLinkedDeque");

            // Use push() method to null element
            CLD.push(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
ConcurrentLinkedDeque: []
Trying to add null in ConcurrentLinkedDeque
java.lang.NullPointerException

```