# 用示例将 Java 中的 TransferQueue 链接到 Array()方法

> 原文:[https://www . geeksforgeeks . org/linkedtransferqueue-to array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-toarray-method-in-java-with-examples/)

**公共对象[] toArray()**

[Java . util . concurrent . LinkedTransferQueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **toArray()** 方法是一个内置函数，是 Java，用来形成一个与 LinkedTransferqueue 相同元素的数组。基本上，它将所有元素从 LinkedTransferQueue 复制到新数组中。

**语法:**

```
public Object[] toArray()
```

**参数:**该方法不接受任何参数。

**返回:**这个方法返回一个包含这个队列所有元素的数组，作为它的数组表示。

**异常:**此方法不抛出任何异常。

下面的程序说明了 LinkedTransferQueue 类的 toArray()函数:

**程序 1:**

```
// Java code to illustrate
// toarray() method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("GeeksforGeeks");
        LTQ.add("GFG");
        LTQ.add("Geeks");
        LTQ.add("gfg");

        // Get the array using toArray() method
        Object[] obj = LTQ.toArray();

        // Print the LTQ
        System.out.println("Linked Transfer Queue: "
                           + LTQ);

        // Print the array
        System.out.println("Array representation: "
                           + Arrays.toString(obj));
    }
}
```

**Output:**

```
Linked Transfer Queue: [GeeksforGeeks, GFG, Geeks, gfg]
Array representation: [GeeksforGeeks, GFG, Geeks, gfg]

```

**公共 T[] toArray(T[] a)**

[Java . util . concurrent . LinkedTransferQueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/)的 **toArray()** 方法是一个内置函数，是 Java，用于形成一个与 LinkedTransferqueue 相同元素的数组。它以正确的顺序返回一个包含该 LinkedTransferQueue 中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。如果 LinkedTransferQueue 适合指定的数组，它将在其中返回。否则，将使用指定数组的运行时类型和此 LinkedTransferQueue 的大小分配一个新数组。

**语法:**

```
public T[] toArray (T[] a)
```

**参数:**该方法接受一个参数**a【】**，如果向量足够大，则向量的元素将被存储到该数组中；否则，将为此目的分配一个相同运行时类型的新数组。

**返回:**这个方法返回一个包含这个队列所有元素的数组。

**异常:**该方法抛出以下异常:

*   **arraystorexception**:如果指定数组的运行时类型不是该队列中每个元素的运行时类型的超类型
*   **空指针异常**:如果指定数组为空

**程序 2:**

```
// Java code to illustrate
// toarray(a[]) method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // Create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("Welcome");
        LTQ.add("to");
        LTQ.add("Geeks");
        LTQ.add("for");
        LTQ.add("Geeks");

        // Get the array using toArray() method
        String[] arr = new String[5];
        arr = LTQ.toArray(arr);

        // Print the LTQ
        System.out.println("Linked Transfer Queue: "
                           + LTQ);

        // Print the array
        System.out.println("Array representation: "
                           + Arrays.toString(arr));
    }
}
```

**Output:**

```
Linked Transfer Queue: [Welcome, to, Geeks, for, Geeks]
Array representation: [Welcome, to, Geeks, for, Geeks]

```

**程序 3:** 显示空指针异常的程序。

```
// Java code to illustrate
// toarray(a[]) method of LinkedTransferQueue

import java.util.concurrent.LinkedTransferQueue;
import java.util.*;

public class GFG {
    public static void main(String[] args)
        throws InterruptedException
    {

        // create object of LinkedTransferQueue
        LinkedTransferQueue<String> LTQ
            = new LinkedTransferQueue<String>();

        // Add numbers to end of LinkedTransferQueue
        // using add() method
        LTQ.add("Welcome");
        LTQ.add("to");
        LTQ.add("Geeks");
        LTQ.add("for");
        LTQ.add("Geeks");

        // Print the LTQ
        System.out.println("Linked Transfer Queue: "
                           + LTQ);

        try {
            System.out.println("Trying to get array"
                               + " representation by "
                               + "passing null.");
            LTQ.toArray(null);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
Linked Transfer Queue: [Welcome, to, Geeks, for, Geeks]
Trying to get array representation by passing null.
java.lang.NullPointerException

```

**参考文献:**

*   [https://docs . Oracle . com/en/Java/javae/11/docs/API/Java . base/Java/util/concurrent/linked transfer queue . html # toaarray()](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/concurrent/LinkedTransferQueue.html#toArray())
*   [https://docs . Oracle . com/en/Java/javae/11/docs/API/Java . base/Java/util/concurrent/linked transfer queue . html # toaarray(t % 5b % 5d)](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/concurrent/LinkedTransferQueue.html#toArray(T%5B%5D))