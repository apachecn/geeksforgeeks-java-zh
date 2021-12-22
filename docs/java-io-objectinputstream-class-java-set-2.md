# Java 中的 Java.io.ObjectInputStream 类|集合 2

> 原文:[https://www . geesforgeks . org/Java-io-objectinputstream-class-Java-set-2/](https://www.geeksforgeeks.org/java-io-objectinputstream-class-java-set-2/)

[Java 中的 Java.io.ObjectInputStream 类| Set 1](https://www.geeksforgeeks.org/java-io-objectinputstream-class-java-set-1/)
**注意:**
本文提到的 Java 代码不会在 Online IDE 上运行，因为代码中使用的文件不在线存在。因此，为了验证代码的工作情况，您可以将它们复制到您的系统中，并在那里运行。
**ObjectInputStream 类的更多方法:**

*   **defaultReadObject():Java . io . objectinputstream . defaultReadObject()**从输入流中读取当前类的非静态字段。我们使用序列化类的 readObject()方法来调用这个方法。
    **语法:**

```
public void defaultReadObject()
Parameters : 
-----------
Return : 
void
Exception :
-> IOException : in case of any IO error occurs.
-> ClassNotFoundException : if the class of Object(being serialized) is not found
-> NotActiveException : if the Stream is not reading.
```

*   **ReadObject():Java . io . objectInputStream . ReadObject()**从序列化的类中读取一个对象。此方法用于调用 defaultReadObject。如果默认情况下反序列化该类，则可以使用 readObject 和 writeObject 方法重写该类。
    **语法:**

```
public void defaultReadObject()
Parameters : 
public final Object readObject()
Return : 
void
Exception :
-> IOException : in case of any IO error occurs.
-> ClassNotFoundException : if the class of Object(being serialized) is not found
-> OptionalDataException : if instead of object, primitive data is found.
-> InvalidClassException : is there is something wrong with serialized class
```

*   **available():Java . io . objectinputstream . available()**表示在不被阻塞的情况下可以读取的字节数
    **语法:**

```
public int available()
Parameters : 
-----------
Return : 
no. of bytes of that can be read without being blocked
Exception :
-> IOException : in case of any IO error occurs.
```

*   **close():Java . io . objectinputstream . close()**关闭输入流并释放分配给该流的所有资源
    **语法:**

```
public void close()
Parameters : 
-----------
Return : 
void
Exception :
-> IOException : in case of any IO error occurs.
```

*   **read short():Java . io . objectinputstream . read short()**读取 16 位短。
    **语法:**

```
public short readShort()
Parameters : 
public final Object readObject()
Return : 
reads 16 bit short.
Exception :
-> IOException : in case of any IO error occurs.
-> EOFException : if End of stream is reached
```

*   **readUTF():Java . io . objectinputstream . readUTF()**读取修改后的 UTF-8 (Unicode 转换格式)格式的字符串。UTF -8 表示它使用 8 位块来表示一个字符。
    **语法:**

```
public String readUTF()
Parameters : 
public final Object readObject()
Return : 
reads String in modified UTF-8 (Unicode Transformation Format) format
Exception :
-> IOException : in case of any IO error occurs.
```

*   **skip bytes(int maxlen):Java . io . objectinputstream . skip bytes(int max len)**读取时跳过' max len '字节数。
    **语法:**

```
public int skipBytes(int maxlen)
Parameters : 
maxlen : max. no. of bytes to be skipped
Return : 
no. of bytes to be skipped
Exception :
-> IOException : in case of any IO error occurs.
```

*   **readFully(byte[]目的地):Java . io . objectinputstream . readFully(byte[]目的地)**读取从源到目的地数组的所有字节。
    **语法:**

```
public void readFully(byte[] destination)
Parameters : 
destination : the buffer in which the data is to be read
Return : 
returns the 32 bit float read
Exception :
-> IOException : in case of any IO error occurs.
-> EOFException : if End of stream is reached
```

*   **readFully(byte[] destination，int offset，int maxlen):Java . io . objectinputstream . readFully(byte[]destination，int offset，int maxlen)** 从源数组到目标数组读取一些字节(从 offset 到 maxlen 位置开始)。
    **语法:**

```
public void readFully(byte[] destination, int offset, int maxlen)
Parameters : 
destination : the buffer in which the data is to be read
offset : starting position of the buffer
maxlen : max no. of bytes to be read
Return : 
void
Exception :
-> IOException : in case of any IO error occurs.
-> EOFException : if End of stream is reached
```

*   **readFields():Java . io . objectinputstream . readFields()**从输入流中读取常量字段，并指示名称。
    **语法:**

```
public ObjectInputStream.GetField readFields()
Parameters : 
-------
Return : 
GetField object reading the constant fields
Exception :
-> IOException : in case of any IO error occurs.
-> ClassNotFoundException : if class of serialized object is not found
```

*   **resolveClass():Java . io . objectinputstream . resolveClass(objectstream Class INS _ Class)**将一个实例类加载到指定的 StreamClass 中来代替它。
    **语法:**

```
protected Class resolveClass(ObjectStreamClass desc)

 : means that the class object can be of any type, it is to be specified by the coder.
Parameters : 
INS_class : instance of the specified Stream Class
Return : 
Class Object equivalent to the Specified Stream Class
Exception :
-> IO Exception : if any IO exception occurs
-> ClassNotFoundException : if the argumented class is not available.
```

*   **register validation():Java . io . objectinputstream . register validation(ObjectInputValidation object，int order)** 注册对象进行验证。
    **语法:**

```
public void registerValidation(ObjectInputValidation object, int order)
Parameters : 
-------
Return : 
object : object to be validated 
order : Controls the order of callback. These are processed in no particular order
Exception :
-> NotActiveException : If IO stream is not ready to be read
-> InvalidObjectException : if the argumented object to be validated is NULL.
```

*   **resolve Object(Object o):Java . io . ObjectInputStream . resolve Object(Object o)**将一个对象替换为另一个受信任子类的 ObjectInputStream。在调用
    启用解析对象之前，我们无法替换对象。它在对象被读取后被调用。
    **语法:**

```
protected Object resolveObject(Object o)
Parameters : 
o : object we want to substitute
Return : 
---------
Exception :
-> IOException : If IO error occurs.
```

*   **enableResolveObject():Java . io . ObjectInputStream . enableResolveObject(布尔检查)**允许 ResolveObject 方法将一个对象替换为另一个受信任类的 ObjectInputStream。
    调用 enableResolveObject。它在对象被读取后被调用。
    **语法:**

```
protected boolean enableResolveObject(boolean enable)
Parameters : 
check : "true" to allow resolveObject() method
Return : 
----
```

*   **readClassDescriptor():Java . io . ObjectInputStream . readClassDescriptor()**从序列化流中读取类描述符，如果 ObjectInputStream 接受描述符，则调用此方法。默认情况下，描述符由 readClassDescriptor()方法 acc 调用。对象序列化
    **中定义的格式语法:**

```
protected ObjectStreamClass readClassDescriptor()
Parameters : 
-------
Return : 
reads class descriptor
```

*   **ReadBJExterverride():Java . io . ObjectInputStream . ReadBJExterverride()**使用受保护的无参数构造函数从对象输出流中读取对象
    **语法:**

```
protected Object readObjectOverride()
Parameters : 
-------
Return : 
reads object from the Stream
```

*   **readStreamHeader():Java . io . objectinputstream . readStreamHeader()**允许子类读取和验证它们的头并验证版本号
    **语法:**

```
protected void readStreamHeader()
Parameters : 
-------
Return : 
void
```

*   **resolveproxclass(String[]in _ list):Java . io . resolveproxclass(String[]in _ list)**返回一个代理类，实现那些在代理类描述符中命名的接口。使用这种方法，我们可以从动态代理类
    **语法:**中读取描述符

```
protected Class resolveProxyClass(String[] in_list)
Parameters : 
in_List : interface names list, deserialized in the proxy class descriptor
Return : 
Proxy class for specific Interface mentioned in the list
```