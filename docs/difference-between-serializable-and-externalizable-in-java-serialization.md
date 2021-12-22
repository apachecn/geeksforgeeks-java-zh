# Java 序列化中可序列化和可外化的区别

> 原文:[https://www . geesforgeks . org/Java 中可序列化和可外化序列化的区别/](https://www.geeksforgeeks.org/difference-between-serializable-and-externalizable-in-java-serialization/)

将对象的状态写入文件的过程称为[序列化](https://www.geeksforgeeks.org/serialization-in-java/)，但严格来说，是使用我们可以实现序列化的 [fileOutputStream](https://www.geeksforgeeks.org/fileoutputstream-in-java/) 和 [objectOutputStream](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/) 类将对象从 java 支持的形式转换为文件支持的形式或网络支持的形式的过程。

但是我们只能序列化可序列化的对象。当且仅当相应的类实现了 serializable 接口时，对象才被称为是可序列化的。可序列化接口存在于 [java.io 包](https://www.geeksforgeeks.org/java-io-packag/)中，它不包含任何方法，因此它是一个标记接口。如果我们试图序列化一个不可序列化的对象，那么我们将得到运行时异常，表示[不可序列化异常](https://www.geeksforgeeks.org/object-serialization-inheritance-java/)。

**例:**

## 爪哇

```java
// Java Program to illustrate Serializable

// Importing utility classes
// Importing input output classes
import java.io.*;
import java.util.*;

// Main Class
// Class implementing serializable interface
class serializableDemo implements Serializable {

    // Member variables of this class
    String name;
    int age;
    int jobId;

    // Default constructor
    public serializableDemo(String name, int age, int jobId)
    {
        // This keyword is used to refer
        // current object instance
        this.name = name;
        this.age = age;
        this.jobId = jobId;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Creating an object of class in main() method
        serializableDemo t1
            = new serializableDemo("Ram", 34, 2364);

        // Serialization

        // Saving of object in a file
        FileOutputStream fos
            = new FileOutputStream("abc1.ser");
        ObjectOutputStream oos
            = new ObjectOutputStream(fos);

        // Method for serialization of object
        oos.writeObject(t1);

        System.out.println("Object has been serialized");
        // Deserialization

        // Reading the object from a file
        FileInputStream fis
            = new FileInputStream("abc1.ser");
        ObjectInputStream ois = new ObjectInputStream(fis);

        // Method for deserialization of object
        serializableDemo t2
            = (serializableDemo)ois.readObject();

        // Display message only
        System.out.println("Object has been deserialized ");

        // Print and display the name and age
        // to illustrate Serializable
        System.out.println("Name:" + t2.name + "\n"
                           + "Age:" + t2.age + "\n"
                           + t2.jobId);
    }
}
```