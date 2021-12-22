# Java 中的 FileInputStream getFD()方法，带示例

> 原文:[https://www . geesforgeks . org/file inputstream-getfd-method-in-Java-with-examples/](https://www.geeksforgeeks.org/fileinputstream-getfd-method-in-java-with-examples/)

**Java . io . file inputstream . getfd()**方法是**[**Java . io . file inputstream**](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/)**类的一部分。该方法将返回与文件输入流相关联的[文件描述符](https://www.geeksforgeeks.org/java-io-filedescriptor-java/)对象。****

*   ****getFD()方法被声明为 final，这意味着不能在子类中重写 getFD()****
*   ****我们将使用 getFD()方法获得的 FileDescriptor 对象将表示到文件系统中实际文件的连接****
*   ****方法可能会引发 IOException。****

******语法:******

```java
**public final FileDescriptor getFD() throws IOException**
```

******返回类型:** getFD()方法将返回与此 FileInputStream 关联的 FileDescriptor 的实例。****

******异常:** getFD()方法可能会抛出 **IOException** 如果任何输入/输出异常引发。****

### ****如何调用 getFD()方法？****

******步骤 1:** 首先，我们必须创建一个 Java.io.FileInputStream 类的实例****

```java
**FileInputStream  fileInputStream =new FileInputStream("tmp.txt");**
```

******第 2 步:**要获取与这个 fileInputStream 关联的 FileDescriptor 的实例，我们将调用 getFD()方法****

```java
**FileDescriptor fileDescriptor =fileInputStream.getFD();**
```

#### ****示例:Java 程序获取文件描述符的实例，然后检查它是否有效****

****在下面的程序中，我们将****

*   ****使用 Java.io.FileInputStream.getFD()方法获取 FileDescriptor 的对象****
*   ****使用 FileDescriptor valid()方法检查文件描述符的实例是否有效****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java Program to get an instance
// of FileDescriptor and then to
// check it is valid or not

import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        try {
            // create instance of FileInputStream class
            // user should change name of the file
            FileInputStream fileInputStream
                = new FileInputStream(
                    "C://geeksforgeeks//tmp.txt");

            // if the specified file does not exist
            if (fileInputStream == null) {
                System.out.println(
                    "Cannot find the specified file");
                return;
            }

            // to get the object of FileDescriptor for
            // this specified fileInputStream
            FileDescriptor fileDescriptor
                = fileInputStream.getFD();

            // check if the fileDescriptor is valid or not
            // using it's valid method
            // valid() will return true if valid else false
            System.out.println("Is FileDescriptor valid : "
                               + fileDescriptor.valid());

            // will close the file input stream and releases
            // any system resources associated with the
            // stream.
            fileInputStream.close();
        }
        catch (Exception exception) {
            System.out.println(exception.getMessage());
        }
    }
}**
```

******输出:******

```java
**Is FileDescriptor valid : true**
```

****![](img/3a754515c068b0e1f353ad0a4529d08c.png)

tmp.txt**** 

> ******注意:**程序将在在线 IDE 上运行。请使用脱机集成开发环境，并根据需要更改文件名。****