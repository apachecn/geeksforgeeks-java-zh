# Java 中的 File renameTo()方法，带示例

> 原文:[https://www . geesforgeks . org/file-renameto-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-renameto-method-in-java-with-examples/)

**renameTo()** 方法是[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。renameTo()函数用于将文件的抽象路径名重命名为给定的路径名。如果文件被重命名，函数返回真，否则返回假

**功能签名:**

```
public boolean renameTo(File destination)
```

**语法:**

```
file.renameTo(File destination)
```

**参数:**函数需要 File 对象**目的地**作为参数，当前文件的新抽象路径名。

**返回值:**该函数返回**布尔数据类型**。函数返回真，文件被重命名，否则返回假

**异常:**如果该方法不允许抽象路径名的写操作，则该方法抛出以下异常:

*   **Safety exception** .
*   **null pointer exception** If the target file name is null.

下面的程序将说明 renameTo()函数的使用:

**示例 1:** 尝试将文件 program.txt 重命名为 program1.txt

```
// Java program to demonstrate
// the use of File.renameTo() method

import java.io.*;

public class GFG {

    public static void main(String args[])
    {
        // create an abstract pathname (File object)
        File f = new File("F:\\program.txt");

        // create the destination file object
        File dest = new File("F:\\program1.txt");

        // check if the file can be renamed
        // to the abstract path name
        if (f.renameTo(dest)) {

            // display that the file is renamed
            // to the abstract path name
            System.out.println("File is renamed");
        }
        else {
            // display that the file cannot be renamed
            // to the abstract path name
            System.out.println("File cannot be renamed");
        }
    }
}
```

**输出:**

```
File is renamed
```

**示例 2:** 尝试将“program1.txt”重命名为“prog.txt”，“prog.txt”是 f:驱动器中的现有文件。

```
// Java program to demonstrate
// the use of File.renameTo() method

import java.io.*;

public class GFG {
    public static void main(String args[])
    {
        // create an abstract pathname (File object)
        File f = new File("F:\\program1.txt");

        // create the destination file object
        File dest = new File("F:\\prog.txt");

        // check if the file can be renamed
        // to the abstract path name
        if (f.renameTo(dest)) {

            // display that the file is renamed
            // to the abstract path name
            System.out.println("File is renamed");
        }
        else {
            // display that the file cannot be renamed
            // to the abstract path name
            System.out.println("File cannot be renamed");
        }
    }
}
```

**输出:**

```
File cannot be renamed

```

**程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的路径**