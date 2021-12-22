# Java 中的 ByteArrayInputStream reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-reset-method-in-java-with-examples/)

**reset()** 方法是由 mark()方法调用的 [**的内置方法。它将输入流重新定位到标记的位置。**](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)

**语法**:

```
public void reset()
```

**参数**:该功能不接受任何参数。
**返回值**:函数不返回任何东西。

以下是上述功能的实现:
**程序一:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 5, 6, 7, 8, 9 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        // Use of reset() method :
        // repositioning the stream to marked positions.
        exam.reset();

        System.out.println("\nreset() invoked");
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**Output:** 

```
5
6
7

reset() invoked
5
6
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 1, 2, 3, 4 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        exam.mark(1);

        // Use of reset() method :
        // repositioning the stream to marked positions.
        exam.reset();

        System.out.println("\nreset() invoked");
        System.out.println(exam.read());
        System.out.println(exam.read());
    }
}
```

**Output:** 

```
1
2
3

reset() invoked
4
-1
```

**参考:**T2】https://docs . Oracle . com/javae/10/docs/API/Java/io/bytearrayinput stream . html # reset()T4]