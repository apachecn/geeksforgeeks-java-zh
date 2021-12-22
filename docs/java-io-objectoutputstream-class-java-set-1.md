# Java 中的 Java.io.ObjectOutputStream 类|集合 1

> 原文:[https://www . geesforgeks . org/Java-io-objectoutputstream-class-Java-set-1/](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/)

对象输出流将 Java 对象的原始数据类型和图形写入输出流。可以使用 ObjectInputStream 读取(重构)对象。对象的持久存储可以通过为流使用文件来实现。

*   只有支持 java.io.Serializable 接口的对象才能写入流。每个可序列化对象的类都经过编码，包括类名和类签名、对象的字段和数组的值，以及从初始对象引用的任何其他对象的闭包。
*   Java 对象输出流通常与 Java 对象输出流一起使用。ObjectOutputStream 用于编写 Java 对象，ObjectInputStream 用于再次读取对象。

**施工人员:**

*   **受保护的对象输出流():**为完全重新实现对象输出流的子类提供一种方法，使其不必分配对象输出流的这个实现刚刚使用的私有数据。
*   **对象输出流(输出流输出):**创建写入指定输出流的对象输出流。

**方法:**

*   **受保护的 void annotateClass(Class cl) :** 子类可以实现此方法，以允许类数据存储在流中。默认情况下，此方法不执行任何操作。ObjectInputStream 中对应的方法是 resolveClass。对于流中的每个唯一类，该方法只调用一次。类名和签名将已经被写入流。这个方法可以自由使用 ObjectOutputStream 来保存它认为合适的类的任何表示(例如，类文件的字节)。ObjectInputStream 的相应子类中的 resolveClass 方法必须读取和使用由 annotateClass 编写的任何数据或对象。

```
Syntax :protected void annotateClass(Class cl)
                      throws IOException
Parameters:
cl - the class to annotate custom data for
Throws:
IOException 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream methods
//illustrating annotateClass(Class<?> cl) method

import java.io.*;
class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }

    public static void main(String[] args) throws IOException,
    ClassNotFoundException
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStreamDemo oot = new ObjectOutputStreamDemo(fout);
        Character c = 'A';

        //illustrating annotateClass(Class<?> cl) method
        oot.annotateClass(Character.class);

        //Write the specified object to the ObjectOutputStream
        oot.writeObject(c);

        //flushing the stream
        oot.flush();

        //closing the stream
        oot.close();

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);
        System.out.print(oit.readObject());
        oit.close();
    }
}
```

**输出:**

```
A
```

*   **受保护的 void annotateProxyClass(类 cl) :** 子类可以实现此方法，将自定义数据与动态代理类的描述符一起存储在流中。对于流中的每个唯一代理类描述符，该方法只调用一次。ObjectOutputStream 中此方法的默认实现没有任何作用。
    ObjectInputStream 中对应的方法是 resolveProxyClass。对于重写此方法的 ObjectOutputStream 的给定子类，ObjectInputStream 的相应子类中的 resolveProxyClass 方法必须读取由 annotateProxyClass 编写的任何数据或对象。

```
Syntax :protected void annotateProxyClass(Class cl)
                           throws IOException
Parameters:
cl - the proxy class to annotate custom data for
Throws:
IOException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating annotateProxyClass(Class<?> cl) method
import java.io.*;

class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }

    public static void main(String[] args) throws IOException,
    ClassNotFoundException
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStreamDemo oot = new ObjectOutputStreamDemo(fout);

        Character c = 'A';

        //illustrating annotateProxyClass(Class<?> cl) method
        oot.annotateProxyClass(Character.class);

        //Write the specified object to the ObjectOutputStream
        oot.writeObject(c);

        //flushing
        oot.flush();

        //closing the stream
        oot.close();

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);
        System.out.print(oit.readObject());
        oit.close();
    }
}
```

**输出:**

```
A
```

*   **void close() :** 关闭流。必须调用此方法来释放与流关联的任何资源。

```
Syntax :public void close()
           throws IOException
Throws:
IOException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating close() method

import java.io.*;
class ObjectOutputStreamDemo
{
    public static void main(String[] args) throws IOException
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStream oot = new ObjectOutputStream(fout);
        oot.write(3);

        //illustrating close()
        oot.close();

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);
        System.out.println(oit.read());
        oit.close();
    }
}
```

*   **输出:**

```
3
```

*   **void defaultWriteObject():**将当前类的非静态和非瞬态字段写入此流。这只能从正在序列化的类的 writeObject 方法中调用。如果调用 NotActiveException，它将引发 NotActiveException。

```
Syntax :public void defaultWriteObject()
                        throws IOException
Throws:
IOException 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating defaultWriteObject() method

import java.io.*;
class ObjectOutputStreamDemo
{
    public static void main(String[] arg) throws IOException,
            ClassNotFoundException
    {
            Character a = 'A';
            FileOutputStream fout = new FileOutputStream("file.txt");
            ObjectOutputStream oot = new ObjectOutputStream(fout);
            oot.writeChar(a);
            oot.flush();

            // close the stream
            oot.close();

            FileInputStream fin = new FileInputStream("file.txt");
            ObjectInputStream oit = new ObjectInputStream(fin);

            // reading the character
            System.out.println(oit.readChar());
    }
}
    class demo implements Serializable
    {
        String s = "GeeksfoGeeks";
        private void writeObject(ObjectOutputStream out)
                throws IOException, ClassNotFoundException
        {
            //demonstrating defaultWriteObject()
            out.defaultWriteObject();

        }
    }

     }
```

**输出:**

```
A
```

*   **受保护的空排出():**排出对象输出流中的任何缓冲数据。类似于刷新，但不会将刷新传播到基础流。

```
Syntax :protected void drain()
              throws IOException
Throws:
IOException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream methods
//illustrating drain() method
import java.io.*;
class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }
    public static void main(String[] arg) throws IOException,
            ClassNotFoundException
    {
            FileOutputStream fout = new FileOutputStream("file.txt");
            ObjectOutputStream oot = new ObjectOutputStream(fout);
            ObjectOutputStreamDemo obj = new ObjectOutputStreamDemo(oot);

            //illustrating drain()
            obj.drain();

            //closing the underlying stream
            oot.close();
            fout.close();
    }
}
```

*   **受保护的布尔使能替换对象(布尔使能):**使流能够替换流中的对象。启用后，将为每个被序列化的对象调用 replaceObject 方法。
    如果 enable 为 true，并且安装了安全管理器，则此方法首先使用 serializable permission(“enablereplacement”)权限调用安全管理器的 checkPermission 方法，以确保可以启用流来替换流中的对象。

```
Syntax :protected boolean enableReplaceObject(boolean enable)
                               throws SecurityException
Parameters:
enable - boolean parameter to enable replacement of objects
Returns:
the previous setting before this method was invoked
Throws:
SecurityException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating enableReplaceObject method
import java.io.*;
class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }

    public static void main(String[] args) throws IOException,
        ClassNotFoundException
        {
            FileOutputStream fout = new FileOutputStream("file.txt");
            ObjectOutputStreamDemo oot = new ObjectOutputStreamDemo(fout);
            Character c = 'A';

            //illustrating enableReplaceObject method
            System.out.println(oot.enableReplaceObject(true));

            //Write the specified object to the ObjectOutputStream
            oot.writeObject(c);

            //flushing
            oot.flush();

            //closing the stream
            oot.close();

            FileInputStream fin = new FileInputStream("file.txt");
            ObjectInputStream oit = new ObjectInputStream(fin);
            System.out.print(oit.readObject());
            oit.close();
    }
}
```

**输出:**

```
false
A
```

*   **ObjectOutputStream。PutField putFields():** 检索用于缓冲要写入流的持久字段的对象。当调用 writeFields 方法时，这些字段将被写入流。

```
Syntax :public ObjectOutputStream.PutField putFields()
                                      throws IOException
Returns:
an instance of the class Putfield that holds the serializable fields
Throws:
IOException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating PutField method
import java.io.*;
class ObjectOutputStreamDemo
{
    public static void main(String[] arg) throws IOException,
            ClassNotFoundException
    {
        Character a ='A';
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStream oot = new ObjectOutputStream(fout);
        oot.writeChar(a);
        oot.flush();

        // close the stream
        oot.close();

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);

        // reading the character
        System.out.println(oit.readChar());
    }
}
class demo implements Serializable
{
    private void writeObject(ObjectOutputStream out)
            throws IOException, ClassNotFoundException
    {
        // Retrieve the object used to buffer
        // persistent fields to be written to the stream
        ObjectOutputStream.PutField fields = out.putFields();

    }
}
```

**输出:**

```
A
```

*   **受保护对象替换对象(Object obj):** 此方法将允许 ObjectOutputStream 的受信任子类在序列化期间用一个对象替换另一个对象。在调用 enableReplaceObject 之前，替换对象是禁用的。enableReplaceObject 方法检查请求替换的流是否可信。写入序列化流的每个对象的第一个匹配项被传递给 replaceObject。对该对象的后续引用被对 replaceObject 的原始调用返回的对象替换。为了确保不会无意中暴露对象的私有状态，只有受信任的流可以使用 replaceObject。
    第一次遇到每个对象时，这个方法只调用一次。对该对象的所有后续引用都将被重定向到新对象。此方法应返回要替换的对象或原始对象。
    空值可以作为要替换的对象返回，但是在包含对原始对象的引用的类中可能会导致 NullReferenceException，因为它们可能需要一个对象而不是空值。

```
Syntax :protected Object replaceObject(Object obj)
                        throws IOException
Parameters:
obj - the object to be replaced
Returns:
the alternate object that replaced the specified one
Throws:
IOException
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
//illustrating replaceObject method
import java.io.*;
class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }

    public static void main(String[] args) throws IOException,
    ClassNotFoundException
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStreamDemo oot = new ObjectOutputStreamDemo(fout);
        String a = "forGeeks";
        String b = "Geeks";

        //Write the specified object to the ObjectOutputStream
        oot.writeObject(a);

        //flushing the stream
        oot.flush();

        oot.enableReplaceObject(true);

        //illustrating replaceObject
        System.out.print(oot.replaceObject(b));

        //closing the stream
        oot.close();

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);
        System.out.print(oit.readObject());
        oit.close();
    }
}
```

**输出:**

```
GeeksforGeeks
```

*   **void useProtocolVersion(int version):**指定写入流时要使用的流协议版本。该例程提供了一个钩子，使当前版本的序列化能够以向后兼容先前版本的流格式的格式编写。
    将尽一切努力避免引入额外的向后不兼容性；然而，有时没有其他选择。

```
Syntax :public void useProtocolVersion(int version)
                        throws IOException
Parameters:
version - use ProtocolVersion from java.io.ObjectStreamConstants.
Throws:
IllegalStateException 
IllegalArgumentException
IOException 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
//Java program demonstrating ObjectOutputStream
 //illustrating useProtocolVersion() method
import java.io.*;
class ObjectOutputStreamDemo extends ObjectOutputStream
{
    public ObjectOutputStreamDemo(OutputStream out) throws IOException
    {
        super(out);
    }

    public static void main(String[] args) throws IOException,
        ClassNotFoundException
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStreamDemo oot = new ObjectOutputStreamDemo(fout);
        String a = "forGeeks";
        String b = "Geeks";

        //illustrating useProtocolVersion()
        oot.useProtocolVersion(ObjectStreamConstants.PROTOCOL_VERSION_2);

        //Write the specified object to the ObjectOutputStream
        oot.writeObject(b);
        oot.writeObject(a);

        //flushing the stream
        oot.flush();

        oot.close();
        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);
        System.out.print(oit.readObject());
        System.out.print(oit.readObject());
        oit.close();
    }
}
```

**输出:**

```
GeeksforGeeks
```

**下一篇:** [Java 中的 Java.io.ObjectOutputStream 类|第 2 集](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-2/)

本文由 [**尼尚·夏尔马**](https://www.facebook.com/ChippingEye2766) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。