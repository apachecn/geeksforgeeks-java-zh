# 如何修复 Java . io . streamForceDexception:Java 中无效的类型代码？

> 原文:[https://www . geesforgeks . org/how-fix-Java-io-streamfoldptedexception-invalid-type-code-in-Java/](https://www.geeksforgeeks.org/how-to-fix-java-io-streamcorruptedexception-invalid-type-code-in-java/)

面临以下几个问题:

1.  当您第一次在 java 中使用序列化在文件中写入对象时，即使您一次写入多个对象，在之后读取文件时也不会出现问题。
2.  现在，当您下次尝试使用序列化向该文件追加新对象(相同类型)时，写入文件将会成功完成，没有任何错误。
3.  但是，读取该文件会产生一个问题，并且会引发一个名为 StreamCorruptedException 的异常。

这些问题背后的根本原因或者我们可以说原因如下:

1.  每当我们打开一个文件，并尝试使用 ObjectOutputStream & file outputstream 将一个可序列化的对象附加到文件的末尾时，ObjectOutputStream 会将头写到文件的末尾，以写入对象数据。每次打开文件并写入第一个对象时，ObjectOutputStream 都会在写入对象数据之前将标头写入文件的末尾。
2.  因此，通过这种方式，每当在追加模式下打开文件以使用文件输出流&对象输出流写入对象时，都会多次写入头。

为了解决这些问题，需要实施以下几项措施:

1.  通过扩展 Object Output Stream(继承)&覆盖方法:“*受保护的 void writeStreamHeader()引发 IOException* ，创建您自己的对象输出流类，比如说 **MyObjectOutputStream** 类。”在你的新类中，这个方法应该什么都不用做。
2.  现在第一次写对象**时，即文件长度为 0 时，使用预定义类的对象 *ObjectOutputStream，*使用 write Object()写对象。**
3.  **这将在文件的开头写入标题。**

> ****下一次**无论何时写对象，即当文件长度为> 0 时，使用您定义的类*的对象 MyObjectOutputStream，*使用 writeObject()写对象。因为您已经覆盖了 writeStreamHeader()方法&它什么也不做，所以文件中不会再次写入头。**

****实施:****

**在这里，为了优化程序，一次完成理解，我们将有 3 个不同的 java 类文件对应于它们的可执行 java 类**

1.  **CustomerCollection.java**
2.  **Customer.java**
3.  **Main.java**

****例 1:**CustomerCollection.java**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to illustrate CustomerCollection.java

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Class 1
// helper class
class MyObjectOutputStream extends ObjectOutputStream {

    // Constructor of ths class
    // 1\. Default
    MyObjectOutputStream() throws IOException
    {

        // Super keyword refers to parent class instance
        super();
    }

    // Constructor of ths class
    // 1\. Parameterized constructor
    MyObjectOutputStream(OutputStream o) throws IOException
    {
        super(o);
    }

    // Method of this class
    public void writeStreamHeader() throws IOException
    {
        return;
    }
}

// Class 2
// Helper class
public class CustomerCollection {

    // Getting file from local machine by creating
    // object of File class
    private static File f = new File("BankAccountt.txt");

    // Method 1
    // To read from the file
    public static boolean readFile()
    {
        // Initially setting bool value as false
        boolean status = false;

        // Try block to check for exceptions
        try {

            // Creating new file using File object above
            f.createNewFile();
        }

        // Catch block to handle the exception
        catch (Exception e) {
        }

        // If the file is empty
        if (f.length() != 0) {

            try {

                // If file doesn't exists
                FileInputStream fis = null;

                fis = new FileInputStream(
                    "BankAccountt.txt");
                ObjectInputStream ois
                    = new ObjectInputStream(fis);

                Customer c = null;

                while (fis.available() != 0) {
                    c = (Customer)ois.readObject();
                    long accNo = c.getAccountNumber();

                    // Print customer name and account
                    // number
                    System.out.println(c.getCustomerName()
                                       + " & ");
                    System.out.println(
                        c.getAccountNumber());
                }

                // Closing the connection to release memory
                // resources using close() method
                ois.close();
                fis.close();

                // Once all connection are closed after the
                // desired action change the flag state
                status = true;
            }

            // Catch block to handle the exception
            catch (Exception e) {

                // Print the exception on the console
                // along with display message
                System.out.println("Error Occurred" + e);

                // Exception encountered line is also
                // displayed on console using the
                // printStackTrace() method
                e.printStackTrace();
            }
        }
        return status;
    }

    // Method 2
    // To add a new customer
    public static boolean AddNewCustomer(Customer c)
    {
        // again, setting and initializing the flag boolean
        // value
        boolean status = false;

        // If customer is not present
        if (c != null) {
            // try block to check for exception
            try {

                // Initially assigning the object null to
                // avoid GC involvement
                FileOutputStream fos = null;

                // Creating an new FileOutputStream object
                fos = new FileOutputStream(
                    "BankAccountt.txt", true);

                // If there is nothing to be write onto file
                if (f.length() == 0) {
                    ObjectOutputStream oos
                        = new ObjectOutputStream(fos);
                    oos.writeObject(c);
                    oos.close();
                }

                // There is content in file to be write on
                else {

                    MyObjectOutputStream oos = null;
                    oos = new MyObjectOutputStream(fos);
                    oos.writeObject(c);

                    // Closing the FileOutputStream object
                    // to release memory resources
                    oos.close();
                }

                // Closing the File class object to avoid
                // read-write
                fos.close();
            }

            // Catch block to handle the exceptions
            catch (Exception e) {

                // Print the exception along with the
                // display message
                System.out.println("Error Occurred" + e);
            }

            // Change the flag status
            status = true;
        }

        return status;
    }
}
```

**现在**、**将此代码保存在文件***CustomerCollection.java***中**

****例 2:**Customer.java**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program of Customer.java
import java.io.*;

class Customer implements Serializable {
    // Private class variables
    private String name;
    private long acc_No;

    // Class Constructor
    Customer(String n, long id)
    {
        acc_No = id;
        name = n;
    }

    // Getter methods of class variables
    public String getCustomerName() { return name; }
    public long getAccountNumber() { return acc_No; }
}
```

 **现在**、**将此代码保存在文件***Customer.java***中**

****例 3:**Main.java**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java Program to illustrate Maian.java

// Importing input output classes
import java.io.*;

// Main class
// Here all above helper classes comes into play
public class Main {

    // Main driver method
    public static void main(String[] args)
    {
        // Class objects assigned with constructors
        // Customer input entries
        Customer c1 = new Customer("Rita", 1);
        Customer c2 = new Customer("Sita", 2);

        // Adding new customers as created above
        CustomerCollection.AddNewCustomer(c1);
        CustomerCollection.AddNewCustomer(c2);

        // Display message for better readability and
        // understanding
        System.out.println("****Reading File****");

        // Lastly reading File
        CustomerCollection.readFile();
    }
}
```