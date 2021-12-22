# 使用 Java 将文件从一个目录移动到另一个目录

> 原文:[https://www . geesforgeks . org/move-file-one-directory-other-using-Java/](https://www.geeksforgeeks.org/moving-file-one-directory-another-using-java/)

Java 提供了在目录之间移动文件的功能。这里描述了实现这一点的两种方法。第一种方法利用文件包进行移动，而另一种方法首先将文件复制到目标，然后从源中删除原始副本。

*   **使用文件。Path move()方法:**重命名文件，并将文件永久移动到新位置。
    **语法:**

```java
public static Path move(Path source, Path target, CopyOption..options)
 throws IOException
Parameters: 
source - the path to the file to move
target - the path to the target file 
(may be associated with a different provider to the source path)
options - options specifying how the move should be done
Returns: the path to the target file
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate renaming and
// moving a file permanently to a new location
import java.io.*;
import java.nio.file.Files;
import java.nio.file.*;

public class Test
{
    public static void main(String[] args) throws IOException
    {
        Path temp = Files.move
        (Paths.get("C:\\Users\\Mayank\\Desktop\\44.txt"),
        Paths.get("C:\\Users\\Mayank\\Desktop\\dest\\445.txt"));

        if(temp != null)
        {
            System.out.println("File renamed and moved successfully");
        }
        else
        {
            System.out.println("Failed to move the file");
        }
    }
}
```

**输出:**

```java
File renamed and moved successfully
```

*   **使用 Java.io.File.renameTo()和 Java.io.File.delete()方法:**使用这两种方法复制文件并删除原始文件。
    **renameTo()的语法:**

```java
public boolean renameTo(File dest)
Description: Renames the file denoted by this abstract path name.
Parameters: dest - The new abstract path name for the named file
Returns: true if and only if the renaming succeeded; false otherwise
```

**delete()语法:**

```java
public boolean delete()
Description: Deletes the file or directory 
denoted by this abstract path name.
Returns: true if and only if the file or 
directory is successfully deleted; false otherwise
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate Copying the file
// and deleting the original file
import java.io.*;

public class Test
{
    public static void main(String[] args)
    {
        File file = new File("C:\\Users\\Mayank\\Desktop\\1.txt");

        // renaming the file and moving it to a new location
        if(file.renameTo
           (new File("C:\\Users\\Mayank\\Desktop\\dest\\newFile.txt")))
        {
            // if file copied successfully then delete the original file
            file.delete();
            System.out.println("File moved successfully");
        }
        else
        {
            System.out.println("Failed to move the file");
        }

    }
}
```

**输出**

```java
File moved successfully
```

**参考文献:**

*   Oracle

本文由 **Mayank Kumar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，也可以使用[<u>【contribute.geeksforgeeks.org】</u>](http://www.contribute.geeksforgeeks.org/)写一篇文章，或者把文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。