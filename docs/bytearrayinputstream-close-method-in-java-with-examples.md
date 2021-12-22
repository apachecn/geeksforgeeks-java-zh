# Java 中的 ByteArrayInputStream close()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytearrainputstream-close-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytearrayinputstream-close-method-in-java-with-examples/)

**close()** 方法是**[Java . io . bytearrainputstream](https://www.geeksforgeeks.org/io-bytearrayinputstream-class-java/)**的内置方法，关闭输入流，并将与该流相关联的系统资源释放给垃圾收集器。

**语法** :

```
public void close()
```

**参数**:该功能不接受任何参数。

**返回值**:函数不返回任何内容。

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 1, 2, 3, 4 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);

        // Closes the InputStream
        geek.close();
    }
}
```

**输出:**

```
Use of available() method : 4

```

**程序二:**

```
// Java program to implement
// the above function
import java.io.*;

public class Main {
    public static void main(String[] args) throws Exception
    {

        // Array
        byte[] buffer = { 2, 3, 4, 8, 9 };

        // Create InputStream
        ByteArrayInputStream geek
            = new ByteArrayInputStream(buffer);

        // Use the function to get the number
        // of available
        int number = geek.available();

        // Print
        System.out.println("Use of available() method : "
                           + number);

        // Closes the InputStream
        geek.close();
    }
}
```

**输出:**

```
Use of available() method : 5

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bytearrainputstream . html # close()](https://docs.oracle.com/javase/10/docs/api/java/io/ByteArrayInputStream.html#close())