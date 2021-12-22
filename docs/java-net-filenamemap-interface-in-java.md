# java 中的 java.net.FileNameMap 接口

> 原文:[https://www . geesforgeks . org/Java-net-filenamemap-interface-in-Java/](https://www.geeksforgeeks.org/java-net-filenamemap-interface-in-java/)

**java.net.FileNameMap** 是一个 Java [界面](https://www.geeksforgeeks.org/interfaces-in-java/)。文件名映射界面是**java.net**包的一部分。文件名映射提供了一种在文件名和 MIME 类型字符串之间进行映射的机制。我们可以使用 FileNameMap getContentTypeFor 方法来获取指定文件的 [MIME 类型](https://www.geeksforgeeks.org/mime-media-types/)。

**语法:**

```
public interface FileNameMap
```

### **方法** java.net.FileNameMap 接口

文件名映射接口只包含一个名为的方法:

**getContentTypeFor(字符串文件名)方法–**它是 **java.net.FileNameMap** 界面的一部分。顾名思义，getContentFor 用于获取特定文件的字符串格式的 MIME 类型。

**语法:**

```
String getContentTypeFor(String fileName)
```

**方法参数:**该方法只有一个字符串类型的参数。

**方法返回类型:**它有一个字符串返回类型，将返回文件的 MIME 类型。

### **如何调用 getContentTypeFor 方法？**

**步骤 1:** 使用**静态方法从数据文件中加载文件名映射**

```
FileNameMap fileNameMap = URLConnection.getFileNameMap();
```

**第二步:**它调用**file namemap . getcontenttypefor(字符串文件名)**方法，并传递文件名以获得它的 MIME 类型

```
String mimeType = fileNameMap.getContentFor(String nameOfTheFile);
```

**示例:**下面是 java 程序，用于更好地理解 FileNameMap 接口，然后使用 FileNameMap getContentTypeFor()方法获取文件的 MIME 类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demsonstrate the
// working of the FileNameMap interface

import java.io.*;
import java.net.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            FileNameMap fileNameMap
                = URLConnection.getFileNameMap();

            // specify all the fileName whose
            // MIME type we need to know
            String firstFileName = "tmp.txt";
            String secondFileName = "profile.png";
            String thirdFileName = "gfg.mp4";

            // call getContentTypeFor() method for each
            // fileName to get it's MIME type , method will
            // return null if fileName is invalid
            String firstFileMimeType = fileNameMap.getContentTypeFor(firstFileName);
            String secondFileMimeType = fileNameMap.getContentTypeFor(secondFileName);
            String thirdFileMimeType = fileNameMap.getContentTypeFor(thirdFileName);

            // print all the MIME types
            System.out.println("Mime type of "
                               + firstFileName + " is "
                               + firstFileMimeType);
            System.out.println("Mime type of "
                               + secondFileName + " is "
                               + secondFileMimeType);
            System.out.println("Mime type of "
                               + thirdFileName + " is "
                               + thirdFileMimeType);
        }
        catch (Exception e) {
            System.out.println("Some Exception "
                               + e.getMessage());
        }
    }
}
```

**Output**

```
Mime type of tmp.txt is text/plain
Mime type of profile.png is image/png
Mime type of gfg.mp4 is video/mp4
```