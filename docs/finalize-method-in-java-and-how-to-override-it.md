# Java 中 finalize()方法以及如何覆盖它

> 原文:[https://www . geesforgeks . org/finalize-method-in-Java-and-how-override-it/](https://www.geeksforgeeks.org/finalize-method-in-java-and-how-to-override-it/)

**[对象类](https://www.geeksforgeeks.org/object-class-in-java/)** 的 **finalize()方法**是[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)总是在删除/销毁符合垃圾收集条件的对象之前调用的方法，以执行清理活动。清理活动意味着关闭与该对象相关联的资源，如数据库连接、网络连接，或者我们可以说资源取消分配。请记住，它不是保留关键字。一旦 finalize 方法完成，垃圾收集器会立即销毁该对象。

**语法:**

```java
protected void finalize throws Throwable{}

```

由于对象类包含 finalize 方法，因此 finalize 方法可用于每个 java 类，因为对象是所有 java 类的超类。因为它对每个 java 类都可用，所以垃圾收集器可以在任何 java 对象上调用 finalize 方法

**为什么使用 finalize 方法()？**
finalize()方法在垃圾收集器为特定对象运行之前释放系统资源。JVM 允许每个对象只调用一次 finalize()。

**如何覆盖 finalize()方法？**

现在[对象类](https://www.geeksforgeeks.org/object-class-in-java/)中存在的 finalize 方法有一个**空实现**，在我们的类清理活动中有，那么我们必须**覆盖这个方法**来定义我们自己的清理活动。

为了[覆盖这个方法](https://www.geeksforgeeks.org/overriding-in-java/)，我们必须在代码中显式定义和调用 finalize。

```java
// Java code to show the
// overriding of finalize() method

import java.lang.*;

// Defining a class demo since every java class
// is a subclass of predefined Object class
// Therefore demo is a subclass of Object class
public class demo {

    protected void finalize() throws Throwable
    {
        try {

            System.out.println("inside demo's finalize()");
        }
        catch (Throwable e) {

            throw e;
        }
        finally {

            System.out.println("Calling finalize method"
                               + " of the Object class");

            // Calling finalize() of Object class
            super.finalize();
        }
    }

    // Driver code
    public static void main(String[] args) throws Throwable
    {

        // Creating demo's object
        demo d = new demo();

        // Calling finalize of demo
        d.finalize();
    }
}
```

**Output:**

```java
inside demo's finalize()
Calling finalize method of the Object class

```