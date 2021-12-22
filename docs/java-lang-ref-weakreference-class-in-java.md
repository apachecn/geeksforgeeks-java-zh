# java 中的 java.lang.ref.WeakReference 类

> 原文:[https://www . geesforgeks . org/Java-lang-ref-weakreference-class-in-Java/](https://www.geeksforgeeks.org/java-lang-ref-weakreference-class-in-java/)

当我们用 Java 创建一个对象时，默认情况下对象并不脆弱。要创建弱引用对象，我们必须向 JVM 显式指定它。

**为什么使用弱参考对象:**

与 C/C++不同，Java 支持动态垃圾收集。这是在 JVM 运行垃圾收集器时执行的。为了不浪费空间，垃圾收集器删除所有**不可到达的对象。**但是，为了标记一个对象进行垃圾收集，我们可以创建一个弱引用对象。

![](img/0c3e2a20785a64550e7b37481bb99d2e.png)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to show the usage of
// java.lang.ref.WeakReference Class
import java.lang.ref.WeakReference;
class GFG {
    public static void main(String[] args)
    {
        // creating a strong object of MyClass
        MyClass obj = new MyClass();

        // creating a weak reference of type MyClass
        WeakReference<MyClass> wobj
            = new WeakReference<>(obj);
        System.out.println(
            "-> Calling Display Function using strong object:");
        obj.Display();
        System.out.println("-> Object set to null");
        obj = null;
        obj = wobj.get();
        System.out.println(
            "-> Calling Display Function after retrieving from weak Object");
        obj.Display();
    }
}
class MyClass {
    void Display()
    {
        System.out.println("Display Function invoked ...");
    }
}
```