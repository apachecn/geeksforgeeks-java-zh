# 用示例链接 Java 中的 TransferQueue transfer()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-transfer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-transfer-method-in-java-with-examples/)

类[的 **transfer()** 方法 LinkedTransferQueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/) 是 Java 中的一个内置函数，一般用于将一个元素传递给等待接收它的线程，如果没有等待的线程，那么它将一直等待，直到等待的线程一到达，线程就进入等待状态，元素将被传递到其中。

**语法:**

```java
public void transfer(E e)

```

**参数:**该方法接受一个强制参数 **e** ，该参数是要传递给处于等待状态的线程的元素。

**返回值:**此方法不返回任何内容，因此返回类型为 void。。

**异常:**该方法抛出以下异常:

*   **空指针异常:**如果程序试图使用具有空值的对象引用。
*   **中断异常:**如果在线程等待或睡眠时中断。

下面的程序说明了 Java 中的 LinkedTransferQueue.transfer()方法:

**程序 1:** 说明 Java 中的 LinkedTransferQueue.transfer()方法。

```java
// Java program to illustrate
// LinkedTransferQueue.transfer() method

import java.util.*;
import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        LinkedTransferQueue<String> g
            = new LinkedTransferQueue<String>();

        new Thread(new Runnable() {

            public void run()
            {
                try {
                    System.out.println("Transferring"
                                       + " an element");

                    // Transfer a String element
                    // using transfer() method
                    g.transfer("is a computer"
                               + " science portal.");
                    System.out.println("Element "
                                       + "transfer is complete");
                }
                catch (InterruptedException e1) {
                    System.out.println(e1);
                }
                catch (NullPointerException e2) {
                    System.out.println(e2);
                }
            }
        }).start();

        try {

            // Get the transferred element
            System.out.println("Geeks for Geeks "
                               + g.take());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Transferring an element
Geeks for Geeks is a computer science portal.
Element transfer is complete

```

**程序 2:** 说明空指针异常

```java
// Java program to illustrate
// LinkedTransferQueue.transfer() method

import java.util.*;
import java.util.concurrent.*;

class GFG {
    public static void main(String args[])
    {

        LinkedTransferQueue<String> g
            = new LinkedTransferQueue<String>();

        new Thread(new Runnable() {

            public void run()
            {
                try {
                    System.out.println("Transferring"
                                       + " an element");

                    // Transfer a null element
                    // using transfer() method
                    g.transfer(null);

                    System.out.println("Element "
                                       + "transfer is complete");
                }
                catch (Exception e) {
                    System.out.println(e);
                    System.exit(0);
                }
            }
        }).start();

        try {

            // Get the transferred element
            System.out.println("Geeks for Geeks "
                               + g.take());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
Transferring an element
java.lang.NullPointerException

```