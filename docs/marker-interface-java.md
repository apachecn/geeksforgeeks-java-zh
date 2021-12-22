# Java 中的标记接口

> 原文:[https://www.geeksforgeeks.org/marker-interface-java/](https://www.geeksforgeeks.org/marker-interface-java/)

它是一个空接口(没有字段或方法)。标记接口的例子有可序列化、可克隆和远程接口。所有这些接口都是空接口。

```
public interface Serializable 
{
  // nothing here
}
```

实时应用中使用的标记接口示例:

1.  **可克隆接口**:Java . lang 包中有可克隆接口。[对象](https://www.geeksforgeeks.org/object-class-in-java/)类中有一个方法克隆()。实现可克隆接口的类表示 clone()方法可以合法地对该类的实例进行逐个字段的复制。
    在不实现可克隆接口的类实例上调用对象的克隆方法会导致抛出异常 CloneNotSupportedException。按照惯例，实现此接口的类应该重写 Object.clone()方法。
    详见此处。

    ## 爪哇语言（一种计算机语言,尤用于创建网站)

    ```
    // Java program to illustrate Cloneable interface
    import java.lang.Cloneable;

    // By implementing Cloneable interface
    // we make sure that instances of class A
    // can be cloned.
    class A implements Cloneable
    {
        int i;
        String s;

        // A class constructor
        public A(int i,String s)
        {
            this.i = i;
            this.s = s;
        }

        // Overriding clone() method
        // by simply calling Object class
        // clone() method.
        @Override
        protected Object clone()
        throws CloneNotSupportedException
        {
            return super.clone();
        }
    }

    public class Test
    {
        public static void main(String[] args)
            throws CloneNotSupportedException
        {
            A a = new A(20, "GeeksForGeeks");

            // cloning 'a' and holding
            // new cloned object reference in b

            // down-casting as clone() return type is Object
            A b = (A)a.clone();

            System.out.println(b.i);
            System.out.println(b.s);
        }
    }
    ```

    输出:

    ```
    20
    GeeksForGeeks
    ```

2.  **Serializable 接口**:Java . io 包中有 Serializable 接口。它用于使对象有资格将其状态保存到文件中。这叫[系列化](https://www.geeksforgeeks.org/serialization-in-java/)。
    不实现此接口的类不会将其任何状态序列化或反序列化。可序列化类的所有子类型本身都是可序列化的。

    ## Java 语言（一种计算机语言,尤用于创建网站)

    ```
    // Java program to illustrate Serializable interface
    import java.io.*;

    // By implementing Serializable interface
    // we make sure that state of instances of class A
    // can be saved in a file.
    class A implements Serializable
    {
        int i;
        String s;

        // A class constructor
        public A(int i,String s)
        {
            this.i = i;
            this.s = s;
        }
    }

    public class Test
    {
        public static void main(String[] args)
          throws IOException, ClassNotFoundException
        {
            A a = new A(20,"GeeksForGeeks");

            // Serializing 'a'
            FileOutputStream fos = new FileOutputStream("xyz.txt");
            ObjectOutputStream oos = new ObjectOutputStream(fos);
            oos.writeObject(a);

            // De-serializing 'a'
            FileInputStream fis = new FileInputStream("xyz.txt");
            ObjectInputStream ois = new ObjectInputStream(fis);
            A b = (A)ois.readObject();//down-casting object

            System.out.println(b.i+" "+b.s);

            // closing streams
            oos.close();
            ois.close();
        }
    }
    ```

    输出:

    ```
    20 GeeksForGeeks
    ```

3.  **远程接口**:远程接口存在于 java.rmi 包中。远程对象是存储在一台机器上并从另一台机器访问的对象。因此，要使一个对象成为远程对象，我们需要用远程接口标记它。在这里，远程接口用于标识其方法可以从非本地虚拟机调用的接口。任何远程对象都必须直接或间接实现这个接口。RMI ( [远程方法调用](https://www.geeksforgeeks.org/remote-method-invocation-in-java/))提供了一些远程对象实现可以扩展的便利类，这有助于远程对象的创建。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。