# Java 中的文件权限

> 原文:[https://www.geeksforgeeks.org/file-permissions-java/](https://www.geeksforgeeks.org/file-permissions-java/)

Java 提供了许多方法调用来检查和更改文件的权限，例如只读文件可以被更改为具有写权限。当用户想要限制文件上允许的操作时，需要更改文件权限。例如，文件权限可以从写入更改为只读，因为用户不再想编辑文件。

**检查当前文件权限**

一个文件可以有以下任意组合的允许权限:

*   **可执行文件:**测试应用程序是否可以执行这个抽象路径名所表示的文件。
    语法:

```java
public boolean canExecute()
Returns: true if and only if the abstract path name
exists and the application is allowed to execute the file
```

*   **可读:**测试应用程序是否可以读取由这个抽象路径名表示的文件。
    语法:

    ```java
    public boolean canRead()
    Returns: true if and only if the file specified by this
    abstract path name exists and can be read by the application; false otherwise
    ```

    *   **Writable:** Tests whether the application can modify the file denoted by this abstract path name.
    Syntax:

    ```java
    public boolean canWrite()
    Returns: true if and only if the file system actually 
    contains a file denoted by this abstract path name and 
    the application is allowed to write to the file; false otherwise.
    ```

    例如，文件可以是可读和可写的，但不能是可执行的。这里有一个 Java 程序来获取与文件相关的当前权限。

    ```java
    // Java program to check the current file permissions.
    import java.io.*;

    public class Test
    {
        public static void main(String[] args)
        {
            // creating a file instance
            File file = new File("C:\\Users\\Mayank\\Desktop\\1.txt");

            // check if the file exists
            boolean exists = file.exists();
            if(exists == true)
            {
                // printing the permissions associated with the file
                System.out.println("Executable: " + file.canExecute());
                System.out.println("Readable: " + file.canRead());
                System.out.println("Writable: "+ file.canWrite());
            }
            else
            {
                System.out.println("File not found.");
            }
        }
    }
    ```

    **输出**

    ```java
    Executable: true
    Readable: true
    Writable: true
    ```

    **更改文件权限**

    一个文件可以有以下权限的任意组合:
    *   可执行的
    *   易读的
    *   可写的

    以下是更改文件相关权限的方法:

    *   **setExecutable**A convenience method to set the owner’s execute permission for this abstract path name.

        ```java
        public boolean setExecutable(boolean executable)
        Description: 
        Parameters: executable - If true, sets the access 
        permission to allow execute operations;
        if false to disallow execute operations
        Returns: true if and only if the operation succeeded. 
        ```

        如果用户没有权限更改此抽象路径名的访问权限，操作将失败。如果可执行文件为 false，并且基础文件系统没有实现执行权限，则操作将失败。

    *   **setReadable:** A convenience method to set the owner’s read permission for this abstract path name.

        ```java
        public boolean setReadable(boolean readable)
        Parameters: readable - If true, sets the access permission to 
        allow read operations; if false to disallow read operations
        Returns: true if and only if the operation succeeded. 
        ```

        如果用户没有权限更改此抽象路径名的访问权限，操作将失败。如果 readable 为 false，并且基础文件系统没有实现读取权限，则操作将失败。

    *   **setWritable :** A convenience method to set the owner’s write permission for this abstract path name.

        ```java
        public boolean setWritable(boolean writable)
        Parameters: writable - If true, sets the access permission
        to allow write operations; if false to disallow write operations
        Returns: true if and only if the operation succeeded.
        ```

        如果用户没有权限更改此抽象路径名的访问权限，操作将失败。

```java
// Java program to change the file permissions
import java.io.*;

public class Test
{
    public static void main(String[] args)
    {
        // creating a new file instance
        File file = new File("C:\\Users\\Mayank\\Desktop\\1.txt");

        // check if file exists
        boolean exists = file.exists();
        if(exists == true)
        {
            // changing the file permissions
            file.setExecutable(true);
            file.setReadable(true);
            file.setWritable(false);
            System.out.println("File permissions changed.");

            // printing the permissions associated with the file currently
            System.out.println("Executable: " + file.canExecute());
            System.out.println("Readable: " + file.canRead());
            System.out.println("Writable: "+ file.canWrite());

        }
        else
        {
            System.out.println("File not found.");
        }
    }
}
```

**输出**

```java
File permissions changed.
Executable: true
Readable: true
Writable: false
```

**参考文献:**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。