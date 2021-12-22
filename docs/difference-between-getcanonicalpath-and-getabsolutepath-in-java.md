# Java 中 getCanonicalPath()和 getAbsolutePath()的区别

> 原文:[https://www . geeksforgeeks . org/getcanonicalpath-and-getabsolutepath-in-Java/](https://www.geeksforgeeks.org/difference-between-getcanonicalpath-and-getabsolutepath-in-java/)之间的区别

**getCanonicalPath()** 和 **getAbsolutePath()** 方法属于 java 中的 java.io.File 类。而这些方法基本上都是用来获取文件对象在系统目录结构中的路径。

**绝对文件路径**是文件对象的路径名

*   If we use the abstract path to create file objects, the absolute file path is the same as the abstract file path.
*   If we use relative paths to create file objects, then the absolute file path is the path that we get after analyzing the relative path according to the current directory.

**CanonicalFilePath** 是文件对象的路径名

*   If we use the abstract path to create a file object, the canonical file path is the same as the abstract file path.
*   If we use relative paths to create file objects, the canonical file path is both the shortest absolute path and the only path.

举个例子吧。比方说，我们使用路径“**C:/folder 1/folder 2/folder 3/file . txt**”创建一个文件对象。显然，上述路径是一个抽象路径，因此绝对文件路径以及规范文件路径将与上面相同。

但是如果文件对象创建时提到的文件路径像“**C:/folder 1/folder 2/folder 3/folder 4/../../folder3/file.txt** ，那么绝对文件路径将与上述路径相同，但规范文件路径将是最短的绝对路径，即**C:/folder 1/folder 2/folder 3/file . txt”**。

**方法 1:** getAbsolutePath()

```java
public String getAbsolutePath() 
```

**方法 2:** 获取经典路径()

```java
public String getCanonicalPath() throws IOException
```

**示例:**

**方法 1:** getAbsolutePath()

```java
file.getAbsolutePath()    
// It returns absolute path of file object in system's directory structure
```

**方法 2:** 获取经典路径()

```java
file.getCanonicalPath()    
// It returns canonical path of file object in system's directory structure
```

**例 1:**

## 爪哇

```java
// Java Program to illustrate Difference Between
// getCanonicalPath() and getAbsolutePath()

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // Path of Test.txt is E:\workspace\gfg\Test.txt
        // Test.txt is created inside project directory,

        // Here project name is gfg
        File file1 = new File("Test.txt");

        // Getting th absolute path of the file
        // using getAbsolutePath() method
        System.out.println("Absolute Path: "
                           + file1.getAbsolutePath());

        // Getting the canonical path of the file
        // using getCanonicalPath() method
        System.out.println("Canonical Path: "
                           + file1.getCanonicalPath());
    }
}
```