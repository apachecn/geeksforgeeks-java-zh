# Java 中的文件通道类 tryLock()方法，带示例

> 原文:[https://www . geesforgeks . org/file channel-class-try lock-method-in-Java-with-examples/](https://www.geeksforgeeks.org/filechannel-class-trylock-method-in-java-with-examples/)

在[多线程](https://www.geeksforgeeks.org/multithreading-in-java/)程序的情况下，多个线程同时执行，我们需要获取和释放锁来维护进程间的[同步](https://www.geeksforgeeks.org/synchronized-in-java/)。[Java 的 FileChannel 类](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)还提供了一个名为 [*trylock()*](https://www.geeksforgeeks.org/how-to-use-locks-in-multi-threaded-java-program/) 的方法，用于获取指定文件的锁。此方法用于获取在方法参数中指定的文件任何区域的锁。

锁可能是比标准同步块更灵活和复杂的线程同步机制。锁可以是用于控制多个线程对共享资源的访问的工具。通常，锁提供对共享资源的独占访问:一次只有一个线程可以获取锁，每个访问共享资源的人都需要先获取锁。然而，有些锁可能允许对共享资源的并发访问，比如读写锁的读锁。

这里输出的是 ***FileLock 类*** 的对象，其中提到了应用的锁，如果没有应用锁(可能是因为其他进程正在持有或写入文件的原因)，那么这个方法将返回 null。位置变量指定文件的标记，从该标记获取锁，范围(获取锁的范围)由“大小”变量给出。如果没有提到第二个参数，那么龙的大小。默认情况下，取最大值。“共享”布尔变量表明锁是否共享。如果为假，则该锁是独占锁，否则将在其他进程间共享。这些是同步方法的一些基础。它的默认值被认为是假的。

这种方法的主要优点是永远不会被阻塞。调用后，它要么返回获取的锁，要么返回 null(如果文件由另一个进程处理)或者引发异常。此方法通常不同于同一类的 lock()方法，因为在同步过程中，必须等待很长时间才能访问文件或资源并获取锁，但此方法永远不会依次等待，它将返回 null 或异常。

**语法:**方法声明

```
public abstract FileLock tryLock(long position, long size, boolean shared) throws IOException 
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate FileChannel Class
// tryLock() method

// Importing libraries
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.FileLock;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;

// save the file named as GFG.java
public class GFG extends Thread {

    // content to be written in the file.
    String input
        = "geeks for geeks is a learning portal for computer sciences.";

    ByteBuffer buf = ByteBuffer.wrap(input.getBytes());

    // path of the file
    String fp = "gfg.txt";

      // file channel class object
    Path pt = Paths.get(fp);

    public void run()
    {
        try {

            // the thread says if file is opened.
            FileChannel fc = FileChannel.open(
                pt, StandardOpenOption.WRITE,
                StandardOpenOption.APPEND);
            System.out.println(
                Thread.currentThread().getId()
                + "says:File channel is opened for writing");

            // trying lock
            fc.tryLock(0L, Long.MAX_VALUE, false);
            System.out.println(
                Thread.currentThread().getId()
                + "says:acquiring lock");

            // writing
            fc.write(buf);
            // release the Lock after writing
            System.out.print(Thread.currentThread().getId()
                             + "says:");
            System.out.println(
                "writing is done, closing the file");

            // Closing the file connections
            fc.close();
        }

        // Catch block to handle the exception
        catch (Exception e) {
            // Getting and printing current threads
            System.out.println(
                Thread.currentThread().getId()
                + "says: Exception" + e);
        }

        // Here, one file raises exception since the file
        // is being written by another thread.
    }

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Creating an object in the main() method
        GFG g1 = new GFG();
        GFG g2 = new GFG();

        // Calling start() methods over the objects
        g1.start();
        g2.start();

        // Here Two thread in concurrency
        // are trying to access the file
    }
}
```

**输出:**

![](img/b70281d9fe3f69cb995e898c352fa4f3.png)

**输出说明:**

我们正在创建两个线程，试图访问文件并对其执行写操作。因为为了保持同步，我们使用了 *trylock()* 方法。当其中一个线程获取锁并对文件执行操作时，如果第二个线程调用要获取的锁，则方法会引发异常，因为文件不能自由获取。在上面的代码中，我们已经明确地获得了整个文件的锁。如果需要，我们可以更改文件中需要获取锁的部分的大小。