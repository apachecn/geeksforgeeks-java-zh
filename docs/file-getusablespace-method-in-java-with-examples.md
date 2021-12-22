# Java 中的 File getUsableSpace()方法，带示例

> 原文:[https://www . geesforgeks . org/file-getusablespace-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-getusablespace-method-in-java-with-examples/)

**getUsableSpace()** 函数是 Java 中[文件](https://www.geeksforgeeks.org/file-class-in-java/)类的一部分。该函数返回由抽象路径名表示的分区的未分配大小，如果路径名不存在，则返回 0L。这个函数比 getFreeSpace()函数更精确，因为它返回分配给这个虚拟机的空闲空间。该函数给出了分区未分配空间的提示，但不能保证确切的字节数是可用的。如果外部应用程序写入指定的文件，可能会导致错误，那么写入操作可能不会成功。如果没有明确的区别，它将返回与 getFreeSapce()方法相同的值。

**功能签名:**

```java
public long getUsableSpace()
```

**语法:**

```java
long var = file.getUsableSpace();
```

**参数:**此方法不接受任何参数。

**返回值:**该函数返回长数据类型，表示分区的未分配大小(以字节为单位)

**异常:**如果该方法不允许创建文件，则该方法抛出**安全异常**

下面的程序说明了 getUsableSpace()函数的使用:

**示例 1:** 文件“F:\\program.txt”是 F: Directory 中的一个现有文件。

```java
// Java program to demonstrate
// getUsableSpace() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Create an abstract pathname (File object)
        File f = new File("F:\\program.txt");

        // Display the Usable size of the partition
        // using the getUsableSpace() function
        System.out.println("Usable Space: "
                           + f.getUsableSpace());
    }
}
```

**输出:**

```java
Usable Space: 174491860992
```

**示例 2:** 文件“F:\ program 1 . txt”在文件 F:目录中不存在。

```java
// Java program to demonstrate
// getUsableSpace() method of File Class

import java.io.*;

public class solution {
    public static void main(String args[])
    {

        // Create an abstract pathname (File object)
        File f = new File("F:\\program1.txt");

        // Display the Usable size of the partition
        // using the getUsableSpace() function
        System.out.println("Usable Space: "
                           + f.getUsableSpace());
    }
}
```

**输出:**

```java
Usable Space: 0
```

**注意:程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境并设置文件路径。**