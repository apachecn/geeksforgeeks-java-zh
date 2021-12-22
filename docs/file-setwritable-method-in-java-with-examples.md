# Java 中的文件设置可写()方法，示例

> 原文:[https://www . geesforgeks . org/file-set written-method-in-Java-with-examples/](https://www.geeksforgeeks.org/file-setwritable-method-in-java-with-examples/)

**set writely()**方法是[文件](https://www.geeksforgeeks.org/File-class-in-java/)类的一部分。该函数设置所有者或每个人写入抽象路径名的权限。该函数是一个重载函数。一个函数需要两个参数，另一个只需要一个。

**功能签名:**

```java
public boolean setWritable(boolean a, boolean b)
public boolean setWritable(boolean a)
```

**函数语法:**

```java
file.setWritable(boolean a, boolean b)
file.setWritable(boolean a)
```

**参数:**该函数是一个重载函数:

*   **For the first overload:**
    *   如果真值作为第一个参数传递，则允许它写入抽象路径名，否则不允许它写入文件。
    *   如果真值作为第二个参数传递，则写权限仅适用于所有者，否则适用于所有人

    **返回值:**该函数返回一个布尔值，表示操作是否成功。

    **异常:**如果不允许函数对文件进行写访问，该方法抛出**安全异常**。

    下面的程序将说明 setWritable()函数的用法

    **示例 1:** 我们将尝试更改 f:目录中现有文件的所有者的 setWritable 权限。

    ```java
    // Java program to demonstrate the
    // use of setWritable() function

    import java.io.*;

    public class solution {
        public static void main(String args[])
        {

            // try catch block to handle exceptions
            try {

                // Create a file object
                File f = new File("f:\\program.txt");

                // Check if the Writable permission
                // can be set to new value
                if (f.setWritable(true)) {

                    // Display that the Writable permission
                    // is be set to new value
                    System.out.println("Writable permission is set");
                }
                else {

                    // Display that the Writable permission
                    // cannot be set to new value
                    System.out.println("Writable permission cannot be set");
                }
            }
            catch (Exception e) {
                System.err.println(e.getMessage());
            }
        }
    }
    ```

    **输出:**

    ```java
    Writable permission is set

    ```

    **示例 2:** 我们将尝试更改 f:目录中一个现有文件的所有人的 setWritable 权限。

    ```java
    // Java program to demonstrate the
    // use of setWritable() function

    import java.io.*;

    public class solution {
        public static void main(String args[])
        {

            // try-catch block to handle exceptions
            try {

                // Create a file object
                File f = new File("f:\\program.txt");

                // Check if the Writable permission
                // can be set to new value
                if (f.setWritable(true, false)) {

                    // Display that the Writable permission
                    // is be set to new value
                    System.out.println("Writable permission"
                                       + " is set");
                }
                else {

                    // Display that the Writable permission
                    // cannot be set to new value
                    System.out.println("Writable permission"
                                       + " cannot be set");
                }
            }
            catch (Exception e) {
                System.err.println(e.getMessage());
            }
        }
    }
    ```

    **输出:**

    ```java
    Writable permission is set

    ```

    **程序可能无法在在线 IDE 中运行。请使用离线 IDE 并设置文件的父文件**