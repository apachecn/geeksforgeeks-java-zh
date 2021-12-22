# 获取文件最后访问时间的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-获取文件的最后访问时间/](https://www.geeksforgeeks.org/java-program-to-get-the-last-access-time-of-a-file/)

存储大量数据的每个文件也有自己的数据集(称为元数据)，可以用来获取该文件的属性。这种数据类型称为属性。Java 为**访问任何文件的任何属性**提供了基础，如文件的创建时间、上次访问时间、上次修改时间、文件类型等。

这一切都可以通过 java 的**两个重要的包**来完成，即

*   Java . nio . file . *；
*   Java . nio . file . attribute . *；

我们将在这里使用的这个包的两个主要类**是:**

1.  basicfileattribureview
2.  基本属性

**示例:**base cfileattributeview 类**的 readattributes()** 方法将用于获取**base cfileattributes 类**对象中的属性。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to get the last access time of a file

import java.nio.file.*;
import java.nio.file.attribute.*;
import java.util.Scanner;

// save as file named gfg.java
public class gfg {
    public static void main(String[] args) throws Exception
    {

        // reading the file path from the system.
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the file path");

        String s = sc.next();

        // setting the path .
        Path path = FileSystems.getDefault().getPath(s);

        // setting all the file data to the attributes in
        // class file of BasicFileAttributeView.
        BasicFileAttributeView view = Files.getFileAttributeView(
                path, BasicFileAttributeView.class);

        // method to read the file attributes.
        BasicFileAttributes attribute = view.readAttributes();

        // using lastAccessTime() method to print the last
        // access time of that file.
        System.out.println("last access time is :"
                           + attribute.lastAccessTime());
    }
}
```

![](img/4e983ad84d99b6a06cd853b5fbc7b043.png)