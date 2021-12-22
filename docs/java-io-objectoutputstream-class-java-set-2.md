# Java 中的 Java.io.ObjectOutputStream 类|集合 2

> 原文:[https://www . geesforgeks . org/Java-io-objectoutputstream-class-Java-set-2/](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-2/)

[Java 中的 Java.io.ObjectOutputStream 类|集合 1](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/)

**更多方法:**

*   **无效写入(字节[] buf) :** 写入字节数组。该方法将一直阻塞，直到实际写入字节。

    ```java
    Syntax :public void write(byte[] buf)
               throws IOException
    Parameters:
    buf - the data to be written
    Throws:
    IOException 

    ```

*   **无效写入(字节[] buf，int off，int len) :** 写入字节子数组。

    ```java
    Syntax :public void write(byte[] buf,
             int off,
             int len)
               throws IOException
    Parameters: buf - the data to be written
    off - the start offset in the data
    len - the number of bytes that are written
    Throws:
    IOException
    ```

*   **无效写入(int val) :** 写入一个字节。该方法将一直阻塞，直到实际写入字节。

    ```java
    Syntax :public void write(int val)
               throws IOException
    Parameters:
    val - the byte to be written to the stream
    Throws:
    IOException 
    ```

*   **void write 布尔值(布尔值):**写一个布尔值。

    ```java
    Syntax :public void writeBoolean(boolean val)
                      throws IOException
    Parameters:
    val - the boolean to be written
    Throws:
    IOException 
    ```

*   **无效写字节(int val) :** 写一个 8 位字节。

    ```java
    Syntax :public void writeByte(int val)
                   throws IOException
    Parameters:
    val - the byte value to be written
    Throws:
    IOException
    ```

*   **void writeBytes(字符串):**将字符串作为字节序列写入。

    ```java
    Syntax :public void writeBytes(String str)
                    throws IOException
    Parameters:
    str - the String of writeBytes to be written
    Throws:
    IOException
    ```

*   **void writeChar(int val) :** 写入 16 位字符。

    ```java
    Syntax :public void writeChar(int val)
                   throws IOException
    Parameters:
    val - the char value to be written
    Throws:
    IOException
    ```

*   **void writeChars(字符串):**将字符串写成字符序列。

    ```java
    Syntax :public void writeChars(String str)
                    throws IOException
    Parameters: str - the String of chars to be written
    Throws:
    IOException
    ```

*   **受保护的 void writeclass descriptor(objectstream class desc):**将指定的类描述符写入 ObjectOutputStream。类描述符用于标识写入流的对象的类。ObjectOutputStream 的子类可以重写此方法，以自定义将类描述符写入序列化流的方式。然后，ObjectInputStream 中的相应方法 readClassDescriptor 应该被重写，以便从其自定义流表示形式中重构类描述符。默认情况下，此方法根据对象序列化规范中定义的格式编写类描述符。

    ```java
    Syntax :protected void writeClassDescriptor(ObjectStreamClass desc)
                                 throws IOException
    Parameters:
    desc - class descriptor to write to the stream
    Throws:
    IOException
    ```

*   **void write double(double val):**写入 64 位双精度值。

    ```java
    Syntax :public void writeDouble(double val)
                     throws IOException
    Parameters:
    val - the double value to be written
    Throws:
    IOException
    ```

*   **void writeFields() :** 将缓冲的字段写入流。

    ```java
    Syntax :public void writeFields()
                     throws IOException
    Throws:
    IOException
    NotActiveException
    ```

*   **void write float(float val):**写入 32 位浮点。

    ```java
    Syntax :public void writeFloat(float val)
                    throws IOException
    Parameters:
    val - the float value to be written
    Throws:
    IOException 
    ```

*   **void writeInt(Int val) :** 写一个 32 位的 int。

    ```java
    Syntax :public void writeInt(int val)
                  throws IOException
    Parameters:
    val - the integer value to be written
    Throws: IOException

    ```

*   **空写长(长值):**写 64 位长。

    ```java
    Syntax :public void writeLong(long val)
                   throws IOException
    Parameters:
    val - the long value to be written
    Throws:
    IOException 
    ```

*   **void writeObject(对象对象):**将指定的对象写入 ObjectOutputStream。对象的类、类的签名以及类及其所有超类型的非瞬态和非静态字段的值都被写入。可以使用 writeObject 和 readObject 方法重写类的默认序列化。该对象引用的对象是通过传递方式编写的，因此 ObjectInputStream 可以重构一个完整的对象等价图。

    ```java
    Syntax :public final void writeObject(Object obj)
                           throws IOException
    Parameters: obj - the object to be written
    Throws:
    InvalidClassException 
    NotSerializableException 
    IOException
    ```

*   **受保护的 void writeObjectOverride(对象对象):**子类用来覆盖默认 writeObject 方法的方法。此方法由 ObjectInputStream 的受信任子类调用，这些子类使用受保护的 no-arg 构造函数构造了 ObjectInputStream。子类需要提供一个带有修饰符“final”的覆盖方法。

    ```java
    Syntax :protected void writeObjectOverride(Object obj)
                                throws IOException
    Parameters:
    obj - object to be written to the underlying stream
    Throws:
    IOException 
    ```

*   **void writeShort(int val) :** 写 16 位短。

    ```java
    Syntax :public void writeShort(int val)
                    throws IOException
    Parameters:
    val - the short value to be written
    Throws:
    IOException
    ```

*   **受保护的 void writeStreamHeader() :** 提供了 writeStreamHeader 方法，因此子类可以在流中添加或预先添加自己的头。它将幻数和版本写入流。

    ```java
    Syntax :protected void writeStreamHeader()
                              throws IOException
    Throws:
    IOException
    ```

*   **void writeUnshared(Object obj) :** Writes an “unshared” object to the ObjectOutputStream. This method is identical to writeObject, except that it always writes the given object as a new, unique object in the stream (as opposed to a back-reference pointing to a previously serialized instance). Specifically:
    *   通过 writeUnshared 写入的对象总是以与新出现的对象(尚未写入流的对象)相同的方式序列化，而不管该对象之前是否已被写入。
    *   如果 writeObject 用于写入以前使用 writeUnshared 写入的对象，则以前的 writeUnshared 操作将被视为对单独对象的写入。换句话说，ObjectOutputStream 永远不会生成对通过调用 writeUnshared 写入的对象数据的反向引用。

    虽然通过 writeUnshared 写入对象本身并不能保证在反序列化对象时对该对象的唯一引用，但它允许在流中多次定义单个对象，因此接收器对 readUnshared 的多次调用不会发生冲突。请注意，上述规则仅适用于用 writeUnshared 编写的基级对象，而不适用于要序列化的对象图中的任何传递引用的子对象。
    覆盖此方法的 ObjectOutputStream 子类只能在拥有“enablesubclass implementation”serializable permission 的安全上下文中构造；任何在没有这个权限的情况下实例化这样一个子类的尝试都会导致抛出一个 SecurityException。

    ```java
    Syntax :public void writeUnshared(Object obj)
                       throws IOException
    Parameters:
    obj - object to write to stream
    Throws: NotSerializableException
    InvalidClassException
    IOException 
    ```

*   **void writeUTF(字符串):**以修改后的 UTF-8 格式写入该字符串的原始数据。请注意，将字符串作为原始数据或对象写入流中有很大的区别。writeObject 编写的字符串实例最初作为字符串写入流中。Future writeObject()调用将对字符串的引用写入流中。

    ```java
    Syntax :public void writeUTF(String str)
                  throws IOException
    Parameters:
    str - the String to be written
    Throws:
    IOException
    ```

*   **虚空冲():**冲溪。这将写入任何缓冲的输出字节，并刷新到基础流。

    ```java
    Syntax :public void flush()
               throws IOException
    Throws:
    IOException
    ```

**程序:**

```java
//Java program demonstrating ObjectOutputStream
//write methods
import java.io.*;
class ObjectOutputStreamDemo
{
    public static void main(String[] args) throws IOException, ClassNotFoundException 
    {
        FileOutputStream fout = new FileOutputStream("file.txt");
        ObjectOutputStream oot = new ObjectOutputStream(fout);

        String a = "GeeksforGeeks";
        String b = "Geek";
        byte[] be = {'A','B','C'};

        //illustrating write()
        oot.write(1);

        //illustrating writeInt(int i)
        oot.writeInt(1);

        //illustrating writeBoolean(boolean a)
        oot.writeBoolean(true);

        //illustrating writeObject(Object x)
        oot.writeObject(a);

        //illustrating writeByte(byte a)
        oot.writeByte(65);

        //illustrating writeBytes(String b)
        oot.writeBytes(b);

        //illustrating writeDouble(double d)
        oot.writeDouble(2.3);

        //illustrating writeUTF(String str)
        oot.writeUTF(a);

        //illustrating writeFloat(float x)
        oot.writeFloat(2.42f);

        //illustrating writeLone(long x)
        oot.writeLong(234342347908l);

        //illustrating writeChars(String a)
        oot.writeChars(a);

        //illustrating writeShort(int val)
        oot.writeShort(2);

        //illustrating write(byte[] buff)
        oot.write(be);

        //flushing the stream
        oot.flush();

        oot.close();

        byte c[]=new byte[4];
        char c1[]=new char[13];

        FileInputStream fin = new FileInputStream("file.txt");
        ObjectInputStream oit = new ObjectInputStream(fin);

        System.out.println(oit.read());
        System.out.println(oit.readInt());
        System.out.println(oit.readBoolean());
        System.out.println(oit.readObject());
        System.out.println(oit.readByte());
        oit.read(c);

        for (int i = 0; i  < 4 ; i++) 
        {
            System.out.print((char)c[i]);
        }

        System.out.println();
        System.out.println(oit.readDouble());
        System.out.println(oit.readUTF());
        System.out.println(oit.readFloat());
        System.out.println(oit.readLong());

        for (int i = 0; i < 13 ; i++)
        {
            System.out.print(oit.readChar());
        }

        System.out.println();
        System.out.println(oit.readShort());
        oit.readFully(be);

        for (int i = 0; i < 3 ; i++) 
        {
            System.out.print((char)be[i]);
        }
        oit.close();
    }
}
```

**输出:**

```java
1
1
true
GeeksforGeeks
65
Geek
2.3
GeeksforGeeks
2.42
234342347908
GeeksforGeeks
2
ABC
```

**程序 2:**

```java
//Java program illustrating ObjectOutputStream
//write methods
import java.io.*;
class ObjectOutputStreamDemo
{
    public static void main(String[] args) throws IOException,
            ClassNotFoundException
    {
            FileOutputStream out = new FileOutputStream("file.txt");
            ObjectOutputStream oout = new ObjectOutputStream(out);
            oout.writeObject(new demo());

            //illustrating writeUnshared()
            //Writes an "unshared" object to the ObjectOutputStream.
            oout.writeUnshared(14);

            //flush the stream
            oout.flush();

            oout.close();

            FileInputStream fin=new FileInputStream("file.txt");
            ObjectInputStream ois=new ObjectInputStream(fin);

            // read an object from the stream and cast it to demo
            demo obj = (demo)ois.readObject();

            System.out.println( obj.var);
            System.out.println(ois.readUnshared());
    }
}
class demo implements Serializable
{
    static int var = 25;

    // assign a new serialPersistentFields
    private static final ObjectStreamField[] serialPersistentFields = 
    {
        new ObjectStreamField("var", Integer.TYPE)
    };

    private void readObject(ObjectInputStream in)
    throws IOException, ClassNotFoundException
    {
        // makes them available by name.
        ObjectInputStream.GetField fields = in.readFields();

        //Get the value of the named int field from the persistent field.
        var = fields.get("var", 0);
    }

    private void writeObject(ObjectOutputStream out)
                throws IOException
    {
        // write into the ObjectStreamField array the variable string
        ObjectOutputStream.PutField fields = out.putFields();
        fields.put("var", var);

        //Write the buffered fields to the stream
        out.writeFields();

    }
}
```

**输出:**

```java
25
14
```

本文由 **[尼尚·夏尔马](https://www.facebook.com/ChippingEye2766)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。