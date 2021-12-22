# Java 中的阻塞方法

> 原文:[https://www.geeksforgeeks.org/blocking-methods-in-java/](https://www.geeksforgeeks.org/blocking-methods-in-java/)

java 中的阻塞方法是阻塞线程直到其操作完成的一组特定方法。因此，他们将不得不阻塞当前线程，直到满足完成任务的条件。因为在本质上，这些方法是阻塞所谓的阻塞方法。例如，[InputStream](https://www.geeksforgeeks.org/java-io-inputstream-class-in-java/)[*read()*](https://www.geeksforgeeks.org/reader-read-method-in-java-with-examples/)方法会阻塞，直到所有 InputStream 数据都被完全读取。下面是一些最常见的 Java 阻塞方法:

1.  Invokedwait (): Wait for the event scheduler thread to execute the code.
2.  InputStream.read (): It blocks until the input data is available, throws an exception, or detects the end of the stream.
3.  ServerSocket.accept (): Listen for inbound Java socket connection and block it until the connection is established.
4.  Countdown.await (): Make the current thread wait until the latch count is zero, unless the thread is interrupted.

阻塞方法有几个缺点:

*   Blocking technology poses a great threat to the scalability of the system. A classic blocking solution includes the method of reducing blocking and using multithreading to serve multiple customers.
*   Design is the most important aspect, because even if a multithreaded system cannot reach a certain point, a poorly designed system can only support hundreds or thousands of threads, because the number of JVM threads is limited.

**实施:**

在下面的示例中，在执行第一个 print 语句后，程序将被第二个 print 语句阻止，直到控制台中输入一些字符。然后单击 enter，因为 read()会阻止该方法，直到某些输入可读为止。

**例 1:**

## Java

```
// Java Program to illsutare Blocking methods

// Importing all input output classes
import java.io.*;

// Class
class GFG {

   // main driver method
   public static void main(String args[]) throws FileNotFoundException, IOException 

   {
     // Print statement
     System.out.println("GFG");

     int result;
     result = System.in.read();

     // Print statement
     System.out.println("Geeks for Geeks");

   } 

}
```

**输出**

```
GFG
Geeks for Geeks
```

**例 2:**

在这个例子中，当一个线程在开始工作之前需要等待其他线程时，使用 CountDownLatch.await()。倒计时()方法减少计数，等待()方法阻塞，直到计数= 0。

## 爪哇

```
// Java Program to illsutare Blocking methods

// Importing all input output classes
import java.io.*;
// Importing concurrent CountDownLatch class
// from java.util package
import java.util.concurrent.CountDownLatch;

// Class
class GFG {

    // Main driver method
    public static void main(String args[])
        throws InterruptedException
    {
        // Let us create task that is going to wait
        // for five threads before it starts
        CountDownLatch latch = new CountDownLatch(4);

        // Creating threads of Person type
        // Custom parameter inputs
        Person p1 = new Person(1500, latch, "PERSON-1");
        Person p2 = new Person(2500, latch, "PERSON-2");
        Person p3 = new Person(3500, latch, "PERSON-3");
        Person p4 = new Person(4500, latch, "PERSON-4");
        Person p5 = new Person(5500, latch, "PERSON-5");

        // Starting the thread
        // using the start() method
        p1.start();
        p2.start();
        p3.start();
        p4.start();
        p5.start();

        // Waiting for the four threads
        // using the latch.await() method
        latch.await();

        // Main thread has started
        System.out.println(Thread.currentThread().getName()
                           + " has finished his work");
    }
}

// Class 2
// Helper class extending Thread class
// To represent threads for which the main thread waits
class Person extends Thread {
    // Member variables of this class
    private int delay;
    private CountDownLatch latch;

    // Method of this class
    public Person(int delay, CountDownLatch latch,
                  String name)
    {
        // super refers to parent class
        super(name);

        // This keyword refers to current object itself
        this.delay = delay;
        this.latch = latch;
    }

    @Override public void run()
    {
        // Try block to check for exceptions
        try {
            Thread.sleep(delay);
            latch.countDown();

            // Print the current thread by getting its name
            // using the getName() method
            // of whose work is completed
            System.out.println(
                Thread.currentThread().getName()
                + " has finished his work");
        }

        // Catch block to handle the exception
        catch (InterruptedException e) {
            // Print the line number where exception occured
            // using the printStackTrace() method
            e.printStackTrace();
        }
    }
}
```

**输出**

```
PERSON-1 has finished his work
PERSON-2 has finished his work
PERSON-3 has finished his work
PERSON-4 has finished his work
main has finished his work
PERSON-5 has finished his work
```