# Java 中的 FileInputStream finalize()方法，带示例

> 原文:[https://www . geesforgeks . org/file inputstream-finalize-method-in-Java-with-examples/](https://www.geeksforgeeks.org/fileinputstream-finalize-method-in-java-with-examples/)

**Java . io . FileInputStream . finalize()**方法是 [Java.io.FileInputStream](https://www.geeksforgeeks.org/java-io-fileinputstream-class-java/) 类的一部分。它确保只要不再存在文件输入流的引用，就调用文件输入流的 close 方法。

*   finalize()方法被注释为[@已弃用。](https://www.geeksforgeeks.org/the-deprecated-annotation-in-java/#:~:text=The%20%40Deprecated%20annotation%20tells%20the,someone%20tries%20to%20use%20it.&text=Methods%20are%20renamed%20for%20consistency,such%20changes%20pose%20a%20problem.)
*   finalize()方法用于在不再存在引用时执行清理操作。
*   finalize()方法可能会引发 IOException。
*   finalize()方法受[保护](https://www.geeksforgeeks.org/protected-keyword-in-java-with-examples/)，这意味着不同的包子类无法访问它们。
*   FileInputStream.finalize()在 [java.io.*](https://www.geeksforgeeks.org/java-io-packag/) 包中提供。

**语法:**

```
protected void finalize​() throws IOException
```

**返回类型:** finalize()方法有一个 void 返回类型，这意味着这个方法不返回任何东西。

**异常:** finalize()方法可能会抛出 **IOException** 如果出现任何输入/输出异常。

### 如何**调用** finalize()方法？

**第 1 步**–首先，我们必须创建一个扩展 FileInputStream 的类，并将 fileName 传递给它的父类。

```
public class GFG extends FileInputStream
{
    public GFG()
    {
        super(fileName);
    }
}
```

**步骤 2**–创建我们在步骤 1 中创建的类的实例

```
GFG gfg=new GFG();
```

**步骤 3**–调用 finalize()方法

```
gfg.finalize();
```

下面的程序将说明**Java . io . FileInputStream . finalize()**方法的使用-

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the use of the
// Java.io.FileInputStream.finalize() method

import java.io.*;
import java.io.FileInputStream;
import java.io.IOException;

public class GFG extends FileInputStream {
    // parameterized constructor
    public GFG(String fileName) throws Exception
    {
        super(fileName);
    }

    public static void main(String[] args)
    {
        try {
            // create instance of GFG class that 
            // extends FileInputStream.
            // user should change name of the file
            GFG gfg = new GFG("C://geeksforgeeks//tmp.txt");

            // reading bytes from file
            System.out.println(
                "Content read from the file before finalize method is called :");

            for (int i = 0; i <= 13; i++)
                System.out.print((char)gfg.read());

            // finalize() method is called.
            // method will perform the cleanup act 
            // if no reference is available
            gfg.finalize();

            // reading bytes again from file
            System.out.println(
                "Content read from the file after finalize method is called :");

            for (int i = 13; i < 47; i++)
                System.out.print((char)gfg.read());
        }
        catch (Throwable t) {
            System.out.println("Some exception");
        }
    }
}
```

**输出-**

```
Content read from the file before finalize method is called :
GeeksForGeeks
Content read from the file after finalize method is called :
is the best website for programmer
```

从输出来看，很明显，我们可以在调用 finalize()方法之前甚至之后读取文件。因为 finalize()方法仅在**不存在引用时执行清理动作**。

![](img/3a754515c068b0e1f353ad0a4529d08c.png)

tmp.txt

> **注意**:程序可能无法在在线 IDE 中运行。请使用脱机集成开发环境，并根据您的需要更改文件名。