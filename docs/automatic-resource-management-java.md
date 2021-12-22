# Java 中的自动资源管理|尝试资源语句

> 原文:[https://www . geesforgeks . org/automatic-resource-management-Java/](https://www.geeksforgeeks.org/automatic-resource-management-java/)

Java 提供了一个功能，使代码更加健壮，并减少了代码行。从 Java 7 开始，这个特性被称为自动资源管理(ARM)，使用**资源试用**。try-with-resources 语句是一个声明一个或多个资源的 try 语句。
此语句确保每个资源都在语句结束时关闭，这有助于在出现错误或成功完成代码块的情况下处理需要处置或关闭的外部资源。

**什么是资源？**
资源是程序使用完之后必须关闭的对象。任何实现 java.lang.AutoCloseable 的对象，包括所有实现 java.io.Closeable 的对象，都可以用作资源。

**旧的资源清理方法–最终使用**

在 JDK 1.7 之前的早期版本的 Java 中，关闭资源是使用 finally 块完成的。

```
// Java program to illustrate cleaning of 
// resources before Java 7

import java.io.*;
import java.util.*;
import java.io.*;
class Resource 
{
    public static void main(String args[]) 
    {
        BufferedReader br = null;
        String str = " ";

        System.out.println("Enter the file path");
        br = new BufferedReader(new InputStreamReader(System.in));

        try
        {
               str = br.readLine();     
        }
        catch(IOException e)
        {
            e.printStackTrace(); 
        } 

        try
        {
            String s;

            // file resource
            br = new BufferedReader(new FileReader(str)); 

            while ((s = br.readLine()) != null) 
            {
                //print all the lines in the text file
                System.out.println(s); 
            }
        } 
        catch (IOException e) 
        {
            e.printStackTrace();
        }

        finally
        {
            try
            {
                if (br != null)

                    //closing the resource in 'finally' block
                    br.close(); 
            } 
            catch (IOException ex) 
            {
                ex.printStackTrace();
            }
        }
    }
}
```

输出:

```
hello
java
```

**新方式——利用资源试用**

在资源尝试方法中，没有使用 finally block。文件资源在小括号内的 try block 中打开。只有这些类的对象可以在实现 AutoCloseable 接口的块中打开，并且这些对象也应该是本地的。无论 try 语句是正常完成还是突然完成，资源都将自动关闭。
**语法:**
以下示例读取文件的第一行。它使用一个 BufferedReader 实例从文件中读取数据。缓冲区缓存器是一种资源，在程序结束后必须关闭:

```
static String readFirstLineFromFile(String path) throws IOException
{
    try (BufferedReader br = new BufferedReader(new FileReader(path)))
    {
        return br.readLine();
    }
}
```

```
// Java program to illustrate 
// Automatic Resource Management 
// in Java without finally block
import java.io.*;
import java.io.*;
import java.util.*;
class Resource 
{
    public static void main(String args[]) 
    {
        String str = ""; 
        BufferedReader br = null;

        System.out.println("Enter the file path");
        br = new BufferedReader(new InputStreamReader(System.in));

        try
        {
            str=br.readLine();
        }
        catch(IOException e)
        {
            e.printStackTrace(); 
        } 

        // try with Resource
        // note the syntax difference
        try (BufferedReader b = new BufferedReader(new FileReader(str)))
        {
            String s;
            while ((s = b.readLine()) != null) 
            {
                System.out.println(s);
            }
        } 
        catch (IOException e) 
        {
            e.printStackTrace();
        }
    }
}
```

输出:

```
hello 
java
```

**多资源自动资源管理**

在资源尝试块中可以使用多个资源，并自动关闭它们。在这种情况下，资源将以它们在括号内创建的相反顺序关闭。

```
// Java program to illustrate 
// Automatic Resource Management 
// in Java with multiple resource
class Resource
{
    public static void main(String s[])
    {
        //note the order of opening the resources
        try(Demo d = new Demo(); Demo1 d1 = new Demo1()) 
        {
            int x = 10/0;
            d.show();
            d1.show1();
        }
        catch(ArithmeticException e)
        {
            System.out.println(e);
        }
    }
}

// custom resource 1
class Demo implements AutoCloseable 
{
    void show()
    {
        System.out.println("inside show");
    }
    public void close()
    {
        System.out.println("close from demo");
    }
}

//custom resource 2
class Demo1 implements AutoCloseable 
{
    void show1()
    {
        System.out.println("inside show1");
    }
    public void close()
    {
        System.out.println("close from demo1");
    }
}
```

输出:

```
close from demo1
close from demo
```

注:在上面的示例中，演示和演示 1 是在尝试块中管理的自定义资源。这些资源需要实现可自动锁定的接口。当我们在特殊的 try-with-resource 块中打开任何此类可自动关闭的资源时，在完成 try 块后，JVM 会立即对 try 块中初始化的所有资源调用 this.close()方法。
**要点:**

1.  最后，在 Java 7 之前，块被用来清理资源。
2.  java 7 之后，资源清理会自动完成。
3.  ARM 是在尝试资源块中初始化资源时完成的，因为接口是自动锁定的。一旦 try 块完成，JVM 就会调用它的 close 方法。
4.  调用 close()方法可能会导致意外的结果。
5.  我们在资源尝试中使用的资源必须是 AutoCloseable 的子类型，以避免编译时错误。
6.  在多资源 ARM 中使用的资源必须按照上述示例中给出的相反顺序关闭

 **参考:**https://docs . Oracle . com/javase/tutorial/essential/exceptions/tryresourcesclose . html。

本文由**阿朴瓦·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。