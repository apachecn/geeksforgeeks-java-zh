# 用示例链接 Java 中的 TransferQueue tryTransfer()方法

> 原文:[https://www . geeksforgeeks . org/link edtransferqueue-try transfer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedtransferqueue-trytransfer-method-in-java-with-examples/)

类[的 **tryTransfer()** 方法 LinkedTransferQueue](https://www.geeksforgeeks.org/linkedtransferqueue-in-java-with-examples/) 是 Java 中的一个内置函数，一般用于将一个元素传递给等待接收它的线程，如果没有等待的线程，那么它将终止，而不会将元素添加到队列中，或者您也可以通过将时间量及其单位作为参数传递给函数来使它等待一定的时间。

在 LinkedTransferQueue 类中，根据传递给它的参数，有两种类型的 tryTransfer()方法。

**try transfer(e)**

通常用于将一个元素转移到处于等待状态的线程，如果没有线程等待，那么它将终止，而不会将该元素添加到队列中

**语法:**

```
public boolean tryTransfer(E e)

```

**参数:**

*   Here **E e** is the element which is to be transferred to the thread which is in waiting state.

    **返回值:**该方法将返回一个**布尔值**，即如果元素被转移则为真，否则为假。

    **异常**:这个方法会抛出以下异常。

    *   **空指针异常**–如果指定的元素为空*   **InterruptedException** – if interrupted while waiting, in which case the element is not left enqueued.

    下面的程序说明了 Java 中简单的 linkedtransferqueue . try transfer()方法:

    **程序 1:** 用 Java 来说明 tryTransfer()方法。

    ```
    // Java program to demonstrate
    // the tryTransfer() Method.

    import java.util.*;
    import java.util.concurrent.*;

    class GFG {
        public static void main(String args[])
        {

            // creating an object
            // for class LinkedTransferQueue
            LinkedTransferQueue<String> g
                = new LinkedTransferQueue<String>();

            new Thread(new Runnable() {

                public void run()
                {

                    try {

                        System.out.println("transferring an element");

                        // calling tryTransfer() method
                        // to transfer the string
                        g.tryTransfer("is a computer science portal.");

                        System.out.println("element transfer is complete");
                    }

                    catch (NullPointerException e2) {

                        System.out.println(e2);
                        System.exit(0);
                    }
                }
            }).start();

            try {

                // here the thread is waiting
                // to receive an element.
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

    ```
    transferring an element
    element transfer is complete
    Geeks for Geeks is a computer science portal.

    ```

    **程序 2:** 空指针异常。

    ```
    // Java program to demonstrate NullPointerException
    // thrown by the tryTransfer() Method.

    import java.util.*;
    import java.util.concurrent.*;

    class GFG {
        public static void main(String args[])
        {

            // create a LinkedTransferQueue object
            LinkedTransferQueue<String> g
                = new LinkedTransferQueue<String>();

            new Thread(new Runnable() {

                public void run()
                {

                    try {
                        System.out.println("transferring an element");

                        // calling tryTransfer() method
                        // to transfer the null element
                        g.tryTransfer(null);

                        System.out.println("element transfer is complete");
                    }

                    catch (NullPointerException e2) {

                        System.out.println(e2);
                        System.exit(0);
                    }
                }
            }).start();

            try {

                System.out.println("Geeks for Geeks " + g.take());

                // here the thread is waiting
                // to receive an element.
            }
            catch (Exception e) {

                System.out.println(e);
                System.exit(0);
            }
        }
    }
    ```

    **Output:**

    ```
    transferring an element
    java.lang.NullPointerException

    ```

    **tryTransfer(E，long timeout，TimeUnit)**

    通常用于将一个元素传递给一个处于等待状态的线程，如果没有线程在等待，那么它就通过将时间量及其单位作为参数传递给函数来等待一定的时间。

    **语法:**

    ```
    public boolean tryTransfer(E e, long timeout, TimeUnit)

    ```

    **参数:**该方法接受三个强制参数:

    *   这里 **E e** 是要传送到处于等待状态的线程的元素。
    *   这里**长超时**是指定终止前应该等待的时间量的时间。
    *   这里**时间单位**是指长时间超时的单位。

    **返回值:**该方法将返回一个**布尔值**。如果元素被转移，则返回 true，否则返回 false。

    **异常**:这个方法会抛出以下异常。

    *   **空指针异常**–如果指定的元素为空*   **InterruptedException** – if interrupted while waiting, in which case the element is not left enqueued.

    **程序 1:** 通过设置等待作为其参数来说明 Java 中的 tryTransfer()方法。

    ```
    // Java program to demonstrate
    // the tryTransfer() Method.

    import java.util.*;
    import java.util.concurrent.*;

    class GFG {
        public static void main(String args[])
        {

            // creating an object for LinkedTransferQueue
            LinkedTransferQueue<String> g
                = new LinkedTransferQueue<String>();

            new Thread(new Runnable() {

                public void run()
                {
                    try {

                        System.out.println("transferring an element");

                        // calling tryTransfer() method passing amount
                        // of time and its units as the parameter
                        // to the function and storing
                        // its return value in a boolean variable.
                        boolean a = g.tryTransfer(
                            "is a computer science portal.",
                            2000,
                            TimeUnit.MILLISECONDS);

                        if (a)
                            System.out.println("element transfer is complete");
                        else
                            System.out.println("element is not transfered ");
                    }
                    catch (NullPointerException e2) {
                        System.out.println(e2);
                    }
                    catch (InterruptedException e3) {
                        System.out.println(e3);
                    }
                }
            }).start();

            try {

                // here thread is made inactive or sleep
                // for 2000 milliseconds
                Thread.sleep(2000);

                // here the thread is ready to receive
                System.out.println("Geeks for Geeks " + g.take());
            }
            catch (Exception e) {
                System.out.println(e);
            }
        }
    }
    ```

    **Output:**

    ```
    transferring an element
    Geeks for Geeks is a computer science portal.
    element transfer is complete

    ```

    **程序 2:** 空指针异常。

    ```
    // Java program to demonstrate NullPointerException
    // thrown by the tryTransfer() Method.

    import java.util.*;
    import java.util.concurrent.*;

    class GFG {
        public static void main(String args[])
        {
            // creating an object
            // for class LinkedTransferQueue
            LinkedTransferQueue<String> g
                = new LinkedTransferQueue<String>();

            new Thread(new Runnable() {

                public void run()
                {
                    try {
                        System.out.println("transferring an element");

                        // calling tryTransfer() method
                        // to transfer the null element
                        g.tryTransfer(null, 2000, TimeUnit.MILLISECONDS);

                        System.out.println("element transfer is complete");
                    }
                    catch (NullPointerException e2) {
                        System.out.println(e2);
                        System.exit(0);
                    }
                    catch (InterruptedException e3) {
                        System.out.println(e3);
                    }
                }
            }).start();

            try {

                // here thread is made inactive or sleep
                // for 2000 milliseconds
                Thread.sleep(2000);

                // here the thread is ready to receive
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

    ```
    transferring an element
    java.lang.NullPointerException

    ```

    **参考文献:**

    *   [https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # try transfer(E)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#tryTransfer(E))
    *   [https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/linkedtransferqueue . html # try transfer(E，%20long，% 20 Java . util . concurrent . time unit)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/LinkedTransferQueue.html#tryTransfer(E, %20long, %20java.util.concurrent.TimeUnit))