# 使用 Java 找到空闲磁盘空间

> 原文:[https://www . geesforgeks . org/find-free-disk-space-use-Java/](https://www.geeksforgeeks.org/find-free-disk-space-using-java/)

java 中有一些方法调用可以用来获取磁盘驱动器的空间相关信息。这些用于获取此类信息的方法在 File 类中声明，该类驻留在 java.io 包中。下面给出了这些方法调用及其使用的细节:
**注意:**这些代码不会在联机 ide 上运行。此外，它们都将在 Java 1.6 和更高版本上工作

1.  **Java.io.File.getFreeSpace()**: Get total free space available in a drive
    **Syntax:**

    ```
    public long getFreeSpace()
    Returns the size of the partition named by this abstract pathname.
    Returns:
    The size, in bytes, of the partition or 0L if this 
    abstract pathname does not name a partition
    Throws:
    SecurityException - If a security manager has been installed and it 
    denies RuntimePermission("getFileSystemAttributes") or its 
    SecurityManager.checkRead(String) method denies read access to the file 
    named by this abstract pathname
    ```

    ```
    // Java program to get the amount of free space available on any drive
    import java.io.*;

    public class Test
    {
        public static void main(String[] args)
        {
            File file = new File("E:\\");

            double size = file.getFreeSpace() / (1024.0 * 1024 * 1024);
            System.out.printf( "%.3f GB\n", size);    
        }
    }
    ```

    输出:

    ```
    18.242 GB
    ```

2.  **Java . io . file . getusablespace()**:一个驱动器可用的总可用空间。返回由该抽象路径名命名的分区上该虚拟机可用的字节数。如果可能，此方法会检查写权限和其他操作系统限制，因此通常会提供比 getFreeSpace()更准确的新数据实际写入量估计。
    返回的可用字节数是一个提示，但不能保证可以使用这些字节中的大部分或任何一个。未分配的字节数很可能在此调用后立即准确。任何外部输入/输出操作，包括在该虚拟机之外的系统上进行的输入/输出操作，都可能使其不准确。此方法不能保证对此文件系统的写操作会成功。
    **语法:**

```
public long getUsableSpace()
Returns:
The number of available bytes on the partition or 0L if the 
abstract pathname does not name a partition. On systems where
this information is not available, this method will be
equivalent to a call to getFreeSpace().
Throws:
SecurityException - If a security manager has been installed and it 
denies RuntimePermission("getFileSystemAttributes") or its
SecurityManager.checkRead(String) method denies read access to the 
file named by this abstract pathname
```

```
import java.io.*;

public class Test
{
    public static void main(String[] args)
    {
        double size = 
              new File("C:\\").getUsableSpace() / (1024.0 * 1024 * 1024);
        System.out.printf( "%.3f GB\n", size);    
    }
}
```

**输出:**

```
62.857 GB
```

9.  **Java.io.File.getTotalSpace()**: Total Capacity of a drive. The method returns the size of the partition named by this abstract pathname.

    **语法:**

    ```
    public long getTotalSpace()
    Returns: Returns:
    The size, in bytes, of the partition or 0L if this abstract pathname 
    does not name a partition
    Throws:
    SecurityException - If a security manager has been installed and it
    denies RuntimePermission("getFileSystemAttributes") or its 
    SecurityManager.checkRead(String) method denies read access to 
    the file named by this abstract pathname
    ```

    ```
    import java.io.*;

    public class Test
    {
        public static void main(String[] args)
        {
            double size = 
                  new File("C:\\").getUsableSpace() / (1024.0 * 1024 * 1024);
            System.out.printf( "%.3f GB\n", size);    
        }
    }
    ```

    **输出:**

    ```
    62.857 GB
    ```

**所用参考:** [甲骨文](https://docs.oracle.com/javase/8/docs/api/java/io/File.html)

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。