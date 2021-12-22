# Java 中的 FileStore getTotalSpace()方法，带示例

> 原文:[https://www . geesforgeks . org/filestore-gettotalspace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/filestore-gettotalspace-method-in-java-with-examples/)

一个**文件存储**类的 **getTotalSpace()** 方法用于返回文件存储的总大小，以字节为单位。此方法将总大小作为长值返回。

**语法:**

```
public abstract long getTotalSpace()
                throws IOException

```

**参数:**此方法不接受任何内容。

**返回值:**该方法将文件存储的**总大小**作为长值返回。

**异常:**如果出现输入输出错误，该方法抛出**异常**。

下面的程序说明了 getTotalSpace()方法:

**程序 1:**

```
// Java program to demonstrate
// FileStore.getTotalSpace() method

import java.io.IOException;
import java.nio.file.FileStore;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {
        // create the object of Path
        Path path
            = Paths.get(
                "E:\\Tutorials\\file.txt");

        // get FileStore object
        try {

            FileStore fs
                = Files.getFileStore(path);

            // print FileStore name and Total size
            System.out.println("FileStore Name: "
                               + fs.name());
            System.out.println("FileStore TotalSpace: "
                               + fs.getTotalSpace());
        }
        catch (IOException e) {

            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```

**输出:**

**程序 2:**

```
// Java program to demonstrate
// FileStore.getTotalSpace() method

import java.io.IOException;
import java.nio.file.FileStore;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class GFG {

    public static void main(String[] args)
    {
        // create the object of Path
        Path path
            = Paths.get(
                "C:\\Movies\\001.txt");

        // get FileStore object
        try {

            FileStore fs
                = Files.getFileStore(path);

            // print FileStore name and Total size
            System.out.println("FileStore Name: "
                               + fs.name());
            System.out.println("FileStore TotalSpace: "
                               + fs.getTotalSpace());
        }
        catch (IOException e) {

            // TODO Auto-generated catch block
            e.printStackTrace();
        }
    }
}
```

**输出:**

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/nio/file/filestore . html # getTotalSpace()](https://docs.oracle.com/javase/10/docs/api/java/nio/file/FileStore.html#getTotalSpace())