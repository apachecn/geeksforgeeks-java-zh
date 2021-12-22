# 演示单例类嵌套初始化的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-演示单例类的嵌套初始化/](https://www.geeksforgeeks.org/java-program-to-demonstrate-the-nested-initialization-for-singleton-class/)

一个[**单例类**](https://www.geeksforgeeks.org/singleton-class-java/#:~:text=In%20object%2Doriented%20programming%2C%20a,to%20the%20first%20instance%20created.) 只能产生一个单独的实例。每个 Singleton 类都有一个返回其对象的 getInstance 方法。当第一次调用 getInstance 方法时，类的一个对象被生成、存储，然后返回。在对 getInstance 的后续调用中，会返回之前生成的相同对象。

**嵌套初始化**可用于制作 Singleton 类。
在下面的实现中，我们使用嵌套初始化创建了一个 Singleton 类。进行以下观察:

*   这个类的默认 no-arg 构造函数是私有的，以防止其他类直接访问它并生成 Singleton 的对象。
*   Singleton 类有一个静态公共 getInstance 方法，Singleton 作为返回类型。这将被其他类用来获取 Singleton 的对象。
*   Singleton 类中有一个**嵌套类**。这个嵌套类有一个存储单例类对象的实例变量。
*   getInstance 方法从该实例变量中获取值，并将其返回到调用站点。

**使用嵌套初始化创建单例类的演示**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate Singleton Class
// using Nested Initialization

class Singleton {

    // a member variable
    String str = "GFG!";

    // Nested class has just 1 role i.e.creation of the
    // Singleton object and storing it in Instance variable
    private static class Nested {
        static Singleton Instance = new Singleton();
    }

    // The getInstance() method returns the object of
    // Singleton class stored in Instance variable
    public static Singleton getInstance()
    {
        return Nested.Instance;
    }

    // no-argument constructor has to be made private
    // this forces other classes to use getInstance() method
    // in order to obtain the instance of Singleton class

    private Singleton()
    {
        System.out.println("Object made");
    }
}

public class Main {

    public static void main(String[] args)
    {
        Singleton obj1 = Singleton.getInstance();
        Singleton obj2 = Singleton.getInstance();

        // make changes to obj1.str and output obj2.str
        obj1.str = "geeksforgeeks!";

        System.out.println(obj2.str);
    }
}
```

**Output**

```java
Object made
geeksforgeeks!

```