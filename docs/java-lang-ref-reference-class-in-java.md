# java 中的 java.lang.ref.Reference 类

> 原文:[https://www . geesforgeks . org/Java-lang-ref-reference-class-in-Java/](https://www.geeksforgeeks.org/java-lang-ref-reference-class-in-java/)

java.lang.ref.Reference Class 是一个[抽象](https://www.geeksforgeeks.org/abstract-keyword-in-java/) [基类](https://www.geeksforgeeks.org/inheritance-in-java/)为[引用](https://www.geeksforgeeks.org/references-in-c/)对象。此类包含用于获取引用对象信息的方法。这个类不是直接的[子类](https://www.geeksforgeeks.org/referencing-subclass-objects-subclass-vs-superclass-reference/)，因为对引用对象的操作是与[垃圾收集器](https://www.geeksforgeeks.org/garbage-collection-java/)紧密配合的。

**类声明:**防止

```
public abstract class Reference<T>
extends Object
```

**方法:**

<figure class="table">

| way | describe |
| --- | --- |
| clear away | This method prevents this reference object from being enqueued by clearing it. Only java code can call this method. The garbage collector can clear references directly. The garbage collector does not need to call this method to clear references. |
| 入队() | This method adds this object to its registration queue. |
| get() | This method is used to get the object pointed by this reference. If java code or garbage collector clears the object at this reference, it returns null. |
| isEnqueued() | This method is used to know whether this reference object has any queues registered. |

</figure>

**1。公共无效清除():**

此方法通过清除此引用对象来防止此对象入队。只有 [java 代码](https://www.geeksforgeeks.org/java/)可以调用这个方法。垃圾收集器可以直接清除引用。垃圾收集器不需要调用这个方法来清除引用。

**2 .public boolean**[**【enqueue()**](https://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/)**:**

此方法将此对象添加到其注册队列中。

**返回:**如果此引用对象已成功添加到注册队列，则为 True 如果此引用对象在创建时未注册到任何队列，则为 false。

**3。公共 T get():**

此方法用于获取此引用所引用的对象。如果 java 代码或垃圾收集器清除了该引用处的对象，则返回 null。

**返回:**该引用所指的对象，如果该对象被清除，则为空。

**4。公共布尔值 isEnqueued():**

这个方法用来知道这个引用对象是否在任何队列中注册。

**如果该引用对象已经入队，则返回:**真，否则返回假

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate working of Reference Class
import java.lang.ref.Reference;
import java.lang.ref.ReferenceQueue;
import java.lang.ref.SoftReference;
class Gfg {
}

public class GFG {

    public static void main(String[] args)
    {
        // Strong Reference
        Gfg g = new Gfg();

        ReferenceQueue<Gfg> q = new ReferenceQueue<Gfg>();

        // Creating Soft Reference to Gfg-type object to
        // which 'g' is also pointing and registering it
        // with q
        Reference<Gfg> softref
            = new SoftReference<Gfg>(g, q);

        g = softref.get();
        System.out.println(g.toString());
        // enqueue softref to its rregistered queue i.e q

        if (softref.enqueue()) {
            System.out.println(
                "Object successfully enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }

        // checking if softref is enqueued or not
        if (softref.isEnqueued()) {
            System.out.println("Object is enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }

        // clearing this reference object
        softref.clear();

        System.out.println("Object cleared");

        // trying to enqueue after clearing
        if (softref.enqueue()) {
            System.out.println(
                "Object successfully enqueued");
        }
        else {
            System.out.println("Object not enqueued");
        }
    }
}
```

**Output**

```
Gfg@214c265e
Object successfully enqueued
Object is enqueued
Object cleared
Object not enqueued

```