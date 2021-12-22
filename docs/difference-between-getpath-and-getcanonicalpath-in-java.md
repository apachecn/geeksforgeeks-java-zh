# Java 中 getPath()和 getCanonicalPath()的区别

> 原文:[https://www . geesforgeks . org/get path-and-getcanonicalpath-in-Java/](https://www.geeksforgeeks.org/difference-between-getpath-and-getcanonicalpath-in-java/)之间的差异

[*getPath()*](https://www.geeksforgeeks.org/file-getpath-method-in-java-with-examples/) *法*是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。这个函数返回给定文件对象的路径。该函数返回一个包含给定文件对象路径的字符串对象，而[*getcanonical Path()*](https://www.geeksforgeeks.org/file-getcanonicalpath-method-in-java-with-examples/)方法是 [Path](https://www.geeksforgeeks.org/Path-class-in-java/) 类的一部分。该函数返回给定文件对象的规范路径名。如果文件对象的路径名是规范的，那么它只返回当前文件对象的路径。规范路径总是绝对且唯一的，函数移除了“.”'..'如果存在的话。现在，两种方法 [getPath()](https://www.geeksforgeeks.org/file-getpath-method-in-java-with-examples/) 和 [getCanonicalPath()](https://www.geeksforgeeks.org/file-getcanonicalpath-method-in-java-with-examples/) 都是 File 类的一部分，都是获取文件系统路径的 File 方法。首先，我们从下面的文件结构中了解两种路径之间的区别。

**图示:**考虑 windows 目录中的随机路径

```
|--D:
   \--Article      
   \--Test
   \--Program
       \--Python
       \--JAVA
           \Program1.java
```

如果路径-*Python/../JAVA/Program1.java* ”被传递，那么 Path 和规范路径的值如下。

*   **路径:** Python\..\JAVA\Program1.java
*   **规范路径:**d:\ Program \ JAVA \ Program 1 . JAVA

现在让我们理解这两种方法的区别

**(一)**理论差异

<figure class="table">

| *getPath()* 方法 | *getCanonicalPath()* 方法 |
| --- | --- |
| 该函数以字符串形式返回抽象路径名。 | 该函数返回给定文件对象的规范路径名。 |
| 返回的路径名可能是绝对路径。 | 规范路径始终是绝对且唯一的路径。 |
| 如果字符串路径名用于创建文件对象，它只返回路径名。 | 如果需要，该方法首先将该路径名转换为绝对形式。为此，它将调用[*getAbsolutePath()*](https://www.geeksforgeeks.org/file-getabsolutepath-method-in-java-with-examples/)方法，然后将其映射到其唯一的形式。 |
| 如果在文件对象的参数中使用了 URL，那么它将删除协议并返回文件名 | 这个方法会移除多余的名称，例如" "和“..”从路径名。它将解析符号链接，并将驱动器号转换为标准大小写。 |
| 这个方法不会抛出任何异常。 | 此方法引发以下异常。*安全异常:*如果无法访问需要的属性值。*输入输出异常:*如果出现输入输出异常。 |
| *示例:*文件 f =新文件(c:\\用户\ \..\\程序\ \。\\file1.txt ")路径:- c:\users\..\程序\。\file1.txt | *示例:*文件 f =新文件(c:\\用户\ \..\\程序\ \。\\file1.txt ")规范路径:- c:\program\file1.txt |

</figure>

**实施:(B)** 实际差异

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the difference
// between getPath() and  getCanonicalPath() function

// Importing input output classes
import java.io.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Try block to check exceptions
        try {

            // Creating a file object
            File f = new File(
                "g:\\gfg\\A(7)PATH\\Test\\..\\file1.txt");

            // Getting the Path of file object
            String path = f.getPath();

            // Getting the Canonical path of the file object
            String canonical = f.getCanonicalPath();

            // Display the file path of the file object
            // and also the Canonical path of file
            System.out.println("Path : " + path);
            System.out.println("Canonical path : "
                               + canonical);
        }

        // Catch block to handle if exception/s occurs
        catch (Exception e) {

            // Exception message is printed where occurred
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
Path (getPath()): g:\gfg\A(7)PATH\Test\..\file1.txt
path (getCanonicalPath()) : G:\gfg\A(7)PATH\file1.txt
```