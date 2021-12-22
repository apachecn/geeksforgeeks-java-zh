# Java 中 bytearainputstream markSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-marksupported-method-in-java-with-examples/)

**markSupported()** 方法是[**Java . io . BytearRainputStream**](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)方法的内置方法，用于测试该输入流是否支持标记和重置方法。ByteArrayInputStreamInputStream 的 markSupported 方法始终返回 true

**语法**:

```java
public boolean markSupported()
```

**参数**:该功能不接受任何参数。
**返回值**:该函数返回一个布尔值。如果此流实例支持标记和重置方法，则返回 true，否则返回 false。

下面是上述功能的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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

        System.out.println("Mark() invocation");

        // Use of markSupported
        boolean check = exam.markSupported();
        System.out.println("markSupported() : "
                           + check);

        if (exam.markSupported()) {

            // Use of reset() method :
            // repositioning the stream to marked positions.
            exam.reset();

            System.out.println("\nreset() invoked");
            System.out.println(exam.read());
            System.out.println(exam.read());
        }
        else {
            System.out.println("reset() method not supported.");
        }
    }
}
```

**Output:** 

```java
5
6
7
Mark() invocation
markSupported() : true

reset() invoked
5
6
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        byte[] buf = { 1, 2, 3 };

        // Create new byte array input stream
        ByteArrayInputStream exam
            = new ByteArrayInputStream(buf);

        // print bytes
        System.out.println(exam.read());
        System.out.println(exam.read());
        System.out.println(exam.read());

        // Use of markSupported
        boolean check = exam.markSupported();

        System.out.println("markSupported() : "
                           + check);

        if (exam.markSupported()) {

            // Use of reset() method :
            // repositioning the stream to marked positions
            exam.reset();

            System.out.println("\nreset() invoked");
            System.out.println(exam.read());
            System.out.println(exam.read());
        }
        else {
            System.out.println("reset() method not supported.");
        }
    }
}
```

**Output:** 

```java
1
2
3
markSupported() : true

reset() invoked
1
2
```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrainputstream . html # markSupported()T4】