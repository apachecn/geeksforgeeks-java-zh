# Java 中的 Java.io.DataOutputStream in】

> 哎哎哎:# t0]https://www . geeksforgeeks . org/data output stream-in-Java/

数据输出流允许应用程序以可移植的方式将基本的 Java 数据类型写入输出流。然后，应用程序可以使用数据输入流将数据读回。在继续讨论这个类的方法之前，让我们讨论一下这个类的构造函数。

**构造函数:**data output stream(output stream out)

创建新的数据输出流，将数据写入指定的基础输出流。现在让我们在实现之前讨论一下这个类的重要方法。**T3】**

**方法 1:** 空隙冲洗()

刷新此数据输出流。

**语法:**

```
public void flush() throws IOException
```

> **注意:**它确实覆盖了类 FilterOutputStream

中的 flush()方法

**抛出异常:** IOException

**方法 2:** 大小()

返回已写入计数器的当前值，即到目前为止写入此数据输出流的字节数

**语法:**

```
public final int size()
```

**返回类型:**写入字段的整数值

**方法 3:** 写()

将从 offset off 开始的指定字节数组中的 len 字节写入基础输出流。

**语法:**

```
void write (byte[] b, int off, int len)
```

**参数:**

*   Byte array
*   int 关闭
*   Length of byte array

**返回类型:**无效

**方法 4:**

**语法** :

```
public void write(byte[] b, int off,int len)
```

> **注意:**覆盖 FilterOutputStream 类中的 write()方法。

**参数:**

*   data
*   Start offset in data
*   Number of bytes to write

例外: IOException

**方法 5:无效写入(int b):**

将指定字节(参数 b 的低 8 位)写入基础输出流。

**语法:**

```
public void write(int b)
throws IOException
```

**返回类型:**参见

**参数:**要写入的字节

**方法 6:** 写布尔()

将布尔值作为 1 字节值写入基础输出流。

**语法:**

```
void writeBoolean (boolean v) 
```

**返回类型:**无效

**参数:**布尔值

**方法 7:** 写布尔()

**语法:**

```
public final void writeBoolean(boolean v)
throws IOException
```

**参数:**要写入的布尔值。

**投掷:**异常

**方法 8:** writeByte()

将一个字节作为 1 字节值写入基础输出流。

**语法:**

```
public final void writeByte(int v)
throws IOException 
```

**参数:**要写入的字节值

**异常抛出:** IOException

**方法 9:** writeChar()

将字符作为 2 字节值写入基础输出流，高字节优先。

**语法:**

```
public final void writeChar(int v)
throws IOException
```

**参数:**要写入的字符值。

**异常** : IOException

**方法 10:** void writeDouble(双 v)

使用 double 类中的 doubleToLongBits 方法将 Double 参数转换为 long，然后将该 long 值作为 8 字节量写入基础输出流，首先是高字节。

**语法:**

```
public final void writeDouble(double v)
throws IOException
```

**参数:**要写入的双精度值

**抛出异常:** IOException

**方法 11:**T2【写浮(浮 v)

使用 float 类中的 floatToIntBits 方法将 Float 参数转换为 int，然后将该 int 值作为 4 字节量写入基础输出流，首先写入 MSB。

**语法:**

```
public final void writeFloat(float v)
throws IOException
```

**返回类型:**无效

**参数:**要写入的浮点值。

**抛出异常:** IOException

**方法 12:** writeInt()

将一个 int 作为四个字节写入基础输出流，高字节优先。

**语法:**

```
public final void writeInt(int v)
throws IOException
```

**参数:**要写入的整数。

**返回类型:**无效

**抛出异常:**将一个 int 作为四个字节写入基础输出流，高字节优先。

**方法 13:** writeLong()

以八个字节的形式向基础输出流写入一个长字节，高字节优先。

**语法:**

```
public final void writeLong(long v)
throws IOException
```

**参数:**长待写。

**投掷:**异常

**方法 14:** writeShort():

以两个字节的形式向基础输出流写入一个短字节，高字节优先。

**返回类型:**无效

**参数:**待写短

**语法:**

```
public final void writeShort(int v)
throws IOException
```

**方法 15:** 写输出(字符串)

使用修改后的 UTF-8 编码，以独立于机器的方式将字符串写入基础输出流。

**参数**:需要写入的字符串

**返回类型:**无效

**异常抛出:** IOException

> **注意:**有一些重要的点需要记住，如下所列:
> 
> *   DataOutputStream 你好 DataInputStream 你叫什么名字。
> *   When a DataOutputStream is closed (by calling close ()), the underlying stream specified by out will also be closed automatically.
> *   There are no more explicit close () method calls. Try the resource structure to solve this problem.

**例:**

## 爪哇

```
// Java Program to Demonstrate DataOutputStream

// Importing required classes
import java.io.*;

// Main class
// DataOutputStreamDemo
class GFG {
        // Main driver method
        public static void main(String args[]) throws IOException {
                // Try block to check for exceptions
                // Writing the data using DataOutputStream
                try ( DataOutputStream dout =
                                                new DataOutputStream(new FileOutputStream("file.dat")) ) {
                        dout.writeDouble(1.1);
                        dout.writeInt(55);
                        dout.writeBoolean(true);
                        dout.writeChar('4');
                }

                catch (FileNotFoundException ex) {
                        System.out.println("Cannot Open the Output File");
                        return;
                }

                // Reading the data back using DataInputStream
                try ( DataInputStream din =
                                                new DataInputStream(new FileInputStream("file.dat")) ) {
                        double a = din.readDouble();
                        int b = din.readInt();

                        boolean c = din.readBoolean();
                        char d = din.readChar();

                        System.out.println("Values: " + a + " " + b + " " + c + " " + d);
                }

                // Catch block to handle FileNotFoundException
                catch (FileNotFoundException e) {
                        System.out.println("Cannot Open the Input File");
                        return;
                }
        }
}
```

**输出:**

```
Values: 1.1 55 true 4
```

> **注:**以上程序使用试玩资源，所以是否需要 JDK 7 或更高版本。

本文由 [**尼尚·夏尔马**](https://www.facebook.com/ChippingEye2766?ref=bookmarks) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。