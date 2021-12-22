# Java 中的 File getAbsoluteFile()方法，带示例

> 原文:[https://www . geesforgeks . org/file-getabsolutefile-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-getabsolutefile-method-in-java-with-examples/)

**getAbsoluteFile()** 方法是[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。该函数返回给定抽象路径名的绝对文件对象。绝对文件或目录指向与给定文件对象相同的文件或目录。

**例如:**如果我们使用路径“program.txt”创建一个文件对象，它将指向保存可执行程序的同一目录中的文件(如果您使用的是 IDE，它将指向您保存程序的文件)。这里上面提到的文件路径是“program.txt”，但是这个路径不是绝对的(即不完整)。函数 getAbsoluteFile()将返回一个文件，该文件的路径将是根目录的绝对(完整)路径。如果文件对象是用绝对路径创建的，那么 getAbsoluteFile()将返回一个与当前文件相似的文件。

**功能签名:**

```
public File getAbsoluteFile()
```

**函数语法:**

```
file.getAbsoluteFile()
```

**参数:**此功能不接受任何参数。

**返回值:**函数返回绝对文件对象，表示与抽象路径名相同的文件或目录。

**异常:**如果无法访问需要的属性值，该方法抛出**安全异常**。

下面的程序将说明 getAbsolutePath()方法的使用:

**示例 1:** 我们在当前工作目录中有一个名为“program.txt”的文件。

```
// Java program to demonstrate the
// use of getAbsoluteFile() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {
        // try-catch block to handle exceptions
        try {

            // create a file object
            File f = new File("program.txt");

            // create a file with the absolute path
            // of file f
            File absolute = f.getAbsoluteFile();

            // display the file path of the file object
            // and also the file path of absolute file
            System.out.println("Original file path : "
                               + f.getPath());
            System.out.println("Absolute file path : "
                               + absolute.getPath());
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
Original file path : program.txt
Absolute file path : C:\Users\pc\eclipse-workspace1\arnab\program.txt

```

![](img/8319443935cf22aa68743166a1f99355.png)

**示例 2:** 我们在当前工作目录中有一个名为“program”的目录。

```
// Java program to demonstrate the
// use of getAbsoluteFile() function

import java.io.*;

public class solution {
    public static void main(String args[])
    {
        // try-catch block to handle exceptions
        try {

            // create a file object
            File f = new File("program");

            // create a file with the absolute path
            // of file f
            File absolute = f.getAbsoluteFile();

            // display the file path of the file object
            // and also the file path of absolute file
            System.out.println("Original file path : "
                               + f.getPath());
            System.out.println("Absolute file path : "
                               + absolute.getPath());
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

```
Original file path : program
Absolute file path : C:\Users\pc\eclipse-workspace1\arnab\program

```

![](img/f01a0605fb3f6a2c9c60cb90a6afd27c.png)

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的路径**