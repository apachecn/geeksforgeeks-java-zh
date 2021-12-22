# Java 中 getPath()和 getAbsolutePath()的区别

> 原文:[https://www . geesforgeks . org/get path-and-getabsolutepath-in-Java/](https://www.geeksforgeeks.org/difference-between-getpath-and-getabsolutepath-in-java/)之间的差异

[**getPath()**](https://www.geeksforgeeks.org/file-getpath-method-in-java-with-examples/)**:**getPath()方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。这个函数返回给定文件对象的路径。该函数返回一个包含给定文件对象路径的字符串对象。

**返回类型:**

```java
The string form of an abstract pathname
```

[**getAbsolutePath()**](https://www.geeksforgeeks.org/file-getabsolutefile-method-in-java-with-examples/)**:**getAbsolutePath()返回一个路径对象，表示给定路径的绝对路径。如果给定的路径名已经是绝对的，那么路径名字符串就像是由 getPath()方法返回的一样。如果当前抽象路径名是空的抽象路径名，则返回当前用户目录的路径名字符串(由系统属性命名)。否则，该路径名将以依赖于系统的方式解析。

**在 Unix 系统上:**

> 通过根据当前用户目录解析相对路径名，相对路径名成为绝对路径名。

**在微软系统上:**

> 相对路径名通过根据路径名命名的驱动器的当前目录进行解析而成为绝对路径名，并根据当前用户目录进行解析。

**返回:**

> 绝对路径名字符串，表示与此抽象路径名相同的文件或目录

### getPath()和 getAbsolutePath()之间的区别

<figure class="table">

|   | getPath（） | getAbsolutePath() |
| --- | --- | --- |
| one | 此方法返回一个字符串，该字符串表示由文件对象表示的文件的(绝对或相对)路径名。 | 此方法返回抽象文件路径名的绝对路径名字符串。

 |
| Two | 如果文件对象是使用绝对路径创建的，那么返回的路径就是绝对路径。 | 如果抽象路径名已经是绝对路径名，则返回相同的路径名字符串。 |
| three | 如果文件对象是使用相对路径创建的，那么返回的路径就是相对路径。 | 如果抽象路径名是相对的，那么它是以系统相关的方式解析的。 |
| four | **示例(在窗户系统上):****如果提供了绝对路径:**文件路径 1 =新文件(“C:\ Users \ \ ASPIRE \ \ Desktop \ \ Java 文件夹\ \ demo . txt”)；**输出:**C:\Users\ASPIRE\Desktop\Java 文件夹\demo.txt如果提供了相对路径:

文件路径 2 =新文件("..\ \ demo . txt ")；**输出:**-什么\demo.txt | **示例(在窗户系统上):**如果提供了绝对路径:文件路径 1 =新文件(“C:\ Users \ \ ASPIRE \ \ Desktop \ \ Java 文件夹\ \ demo . txt”)；**输出:**C:\Users\ASPIRE\Desktop\Java 文件夹\demo.txt如果提供了相对路径:文件路径 2 =新文件("..\ \ demo . txt ")；**输出:**C:\Users\ASPIRE\Desktop\Java 文件夹\..\demo.txt |
| five | **示例(在 Unix 系统上):**如果提供了绝对路径:文件路径 1 =新文件(“home/Pooja/Desktop/Java 文件夹/demo . txt”)；**输出:**主页/Pooja/桌面/Java 文件夹/demo.txt如果提供了相对路径:文件路径 2 =新文件("../demo . txt ")；**输出:**-什么/demo.txt | **示例(在 Unix 系统上):**如果提供了绝对路径:文件路径 1 =新文件(“home/Pooja/Desktop/Java 文件夹/demo . txt”)；**输出:**主页/Pooja/桌面/Java 文件夹/demo.txt如果提供了相对路径:a)文件路径 2 =新文件("../demo . txt ")；**输出:**-什么/demo.txtb)文件路径 2 =新文件("../Document/ABC . txt ")；**输出:**/home/pooja/Document/abc.txt |

</figure>