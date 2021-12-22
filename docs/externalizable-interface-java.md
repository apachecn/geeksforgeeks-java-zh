# Java 中的可外化接口

> 原文:[https://www . geesforgeks . org/experiable-interface-Java/](https://www.geeksforgeeks.org/externalizable-interface-java/)

外部化服务于自定义序列化的目的，在这里我们可以决定在流中存储什么。
Java . io 中存在的可外化接口，用于扩展 Serializable 接口的外化。它由两种方法组成，我们必须覆盖这两种方法才能将对象写入流或从流中读取对象，这两种方法是-

```java
// to read object from stream
void readExternal(ObjectInput in) 

// to write object into stream
void writeExternal(ObjectOutput out) 

```

**可序列化和可外化**
的主要区别

*   **实现:**不像 [Serializable 接口](https://www.geeksforgeeks.org/serialization-in-java/)仅仅通过实现接口就可以序列化对象中的变量，这里我们要明确提到你要序列化哪些字段或者变量。
*   **方法:** Serializable 是没有任何方法的标记接口。可外化接口包含两种方法:writeExternal()和 readExternal()。
*   **流程:**对于实现 Serializable 接口的类，将进行默认的序列化流程。程序员为实现可外化接口的类定义了序列化过程。
*   **向后兼容和控制:**如果必须支持多个版本，可以用 Externalizable 接口进行完全控制。您可以支持不同版本的对象。如果你实现了可外化，序列化超类是你的责任。
*   **公共 No-arg 构造函数:** Serializable 使用反射构造对象，不需要任何 arg 构造函数。但是外部化需要公共的无参数构造函数。

下面是外部化的例子-

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of Externalization
// interface
import java.io.*;
class Car implements Externalizable {
    static int age;
    String name;
    int year;

    public Car()
    {
        System.out.println("Default Constructor called");
    }

    Car(String n, int y)
    {
        this.name = n;
        this.year = y;
        age = 10;
    }

    @Override
    public void writeExternal(ObjectOutput out)
        throws IOException
    {
        out.writeObject(name);
        out.writeInt(age);
        out.writeInt(year);
    }

    @Override
    public void readExternal(ObjectInput in)
        throws IOException, ClassNotFoundException
    {
        name = (String)in.readObject();
        year = in.readInt();
        age = in.readInt();
    }

    @Override public String toString()
    {
        return ("Name: " + name + "\n"
                + "Year: " + year + "\n"
                + "Age: " + age);
    }
}

public class ExternExample {
    public static void main(String[] args)
    {
        Car car = new Car("Shubham", 1995);
        Car newcar = null;

        // Serialize the car
        try {
            FileOutputStream fo
                = new FileOutputStream("gfg.txt");
            ObjectOutputStream so
                = new ObjectOutputStream(fo);
            so.writeObject(car);
            so.flush();
        }
        catch (Exception e) {
            System.out.println(e);
        }

        // Deserializa the car
        try {
            FileInputStream fi
                = new FileInputStream("gfg.txt");
            ObjectInputStream si
                = new ObjectInputStream(fi);
            newcar = (Car)si.readObject();
        }
        catch (Exception e) {
            System.out.println(e);
        }

        System.out.println("The original car is:\n" + car);
        System.out.println("The new car is:\n" + newcar);
    }
}
```

**输出:**

```java
Default Constructor called
The original car is:
Name: Shubham
Year: 1995
Age: 10
The new car is:
Name: Shubham
Year: 1995
Age: 10

```

在这个例子中，类 Car 有两个方法——writeExternal 和 readExternal。因此，当我们将“Car”对象写入 OutputStream 时，会调用 writeExternal 方法来保存数据。这同样适用于 readExternal 方法。
重构可外化对象时，首先使用公共无参数构造函数创建实例，然后调用 readExternal 方法。因此，必须提供无参数构造函数。
当一个对象实现 Serializable 接口，被序列化或反序列化时，没有对象的构造函数被调用，因此在构造函数中实现的任何初始化都无法完成。

本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。