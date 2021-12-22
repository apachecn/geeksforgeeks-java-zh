# Java 中可用的文件输入流()方法，示例

> 原文:[https://www . geesforgeks . org/file inputstream-可用方法-Java-带示例/](https://www.geeksforgeeks.org/fileinputstream-available-method-in-java-with-examples/)

FileInputStream 类的 **available()** 方法用于返回估计的可以从输入流中读取而不阻塞的剩余字节数。此方法返回从文件中读取的剩余字节数。当文件被完全读取时，这个函数返回零。

**语法:**

```
FileInputStream available() 
```

**返回值:**该方法返回并估计从该输入流中读取的剩余字节数，而不阻塞。

**异常:**这个方法可以生成像 IOException 或者 FileNotFoundException 这样的异常。这些例外情况描述如下。

*   **IOException–**如果通过调用 close 关闭了文件输入流，或者发生了任何 I/O 错误。
*   **FileNotFoundException–**如果该目录不可用，那么我们将获得 file notfoundexception。

### **如何调用可用的()方法？**

**步骤 1:** 将文件附加到文件输入流，因为这将使我们能够从文件中读取数据，如下所示:

```
FileInputStream fileInputStream = new FileInputStream(“file.txt”);
```

**第二步:**现在，要从文件中读取有多少数据可供读取的数据，我们应该像下面这样使用 FileInputStream 对象调用一个可用的方法；

```
int ch = fileInputStream.availale(); 
```

**步骤 3(a):** 当没有更多数据可供进一步读取时，available()方法返回 0；

**步骤 3(b):** 然后，我们应该将监视器附加到输出流。为了显示数据，我们可以使用系统打印

```
System.out.print(ch);
```

### **实施**

**原始文件内容:file.txt**

```
GeeksforGeeks
```

这个程序将读取一个文件，并返回每次还有多少字符需要读取。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working
// of the FileInputStream available() method

import java.io.File;
import java.io.FileInputStream;

public class abc {

    public static void main(String[] args)
    {

        // Creating file object and specifying path
        File file = new File("file.txt");

        try {
            FileInputStream input = new FileInputStream(file);
            int character;
            // read character by character by default
            // read() function return int between 0 and 255.

            while ((character = input.read()) != -1) {
                int ch = input.available();
                System.out.print("Currently Reading:"
                                 + (char)character);
                System.out.print(" Remaining character: "
                                 + ch);
                System.out.println();
            }

            input.close();
        }
        catch (Exception e) {

            e.printStackTrace();
        }
    }
}
```

**输出**

```
Currently Reading:G Remaining character: 12
Currently Reading:e Remaining character: 11
Currently Reading:e Remaining character: 10
Currently Reading:k Remaining character: 9
Currently Reading:s Remaining character: 8
Currently Reading:f Remaining character: 7
Currently Reading:o Remaining character: 6
Currently Reading:r Remaining character: 5
Currently Reading:G Remaining character: 4
Currently Reading:e Remaining character: 3
Currently Reading:e Remaining character: 2
Currently Reading:k Remaining character: 1
Currently Reading:s Remaining character: 0
```