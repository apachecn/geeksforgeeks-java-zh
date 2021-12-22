# java 中的 java.lang.ref.PhantomReference 类

> 原文:[https://www . geesforgeks . org/Java-lang-ref-phantom reference-class-in-Java/](https://www.geeksforgeeks.org/java-lang-ref-phantomreference-class-in-java/)

当我们用 Java 创建一个对象时，默认情况下对象是强的。要创建幻影引用对象，我们必须向 JVM 明确指定它。创建虚拟引用对象是因为虚拟引用对象可以进行垃圾收集，但不能立即收集。相反，它被推入一个引用队列中，这样所有这样排队的引用都可以被清除。

![](img/9e8de838de8d089d6bb38dbc851656c1.png)

该类的构造函数如下表所示

<figure class="table">

| Constructor parameter | Constructor description |
| --- | --- |
| 幻影引用(T，参考队列 <t>q):</t> | Create a new phantom reference, which refers to the given object and is registered in the given queue. It is possible to create an empty queue phantom reference, but such a reference is completely useless: its get method will always return null, and since it has no queue, it will never be queued. |

</figure>

从引用类继承的方法如下:

<figure class="table">

| 方法名 | 方法描述 |
| --- | --- |
| get() | 返回此引用对象的引用。因为幻影引用的引用总是不可访问的，所以此方法总是返回 null。 |
| 清除() | 清除此引用对象。调用此方法不会导致此对象入队。 |
| enque() | 将此引用对象添加到注册它的队列中(如果有)。 |
| isEnqueued() | 告知此引用对象是否已由程序或垃圾收集器排入队列。 |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate PhantomReference class
// of java.lang.ref package

// Importing PhantomReference and ReferenceQueue classes
// from java.lanf.ref package
import java.lang.ref.PhantomReference;
import java.lang.ref.ReferenceQueue;

// Class 1
// Helper class
class HelperClass {

    // Method inside HelperClass
    void Display()
    {
        // Print statement whenever the function is called
        System.out.println("Display Function invoked ...");
    }
}

// Class 2
// Main class
public class GFG {
    // MyClass
    // Main driver method
    public static void main(String[] args)
    {
        // Creating a strong object of HelperClass
        HelperClass obj = new HelperClass();

        // Creating a reference queue of HelperClass type
        ReferenceQueue<HelperClass> rq
            = new ReferenceQueue<>();

        // Creating a phantom reference object using rq
        PhantomReference<HelperClass> pobj
            = new PhantomReference<>(obj, rq);

        // Display message only
        System.out.println(
            "-> Calling Display Function using strong object:");

        //  Calling the display method over the object of
        //  HelperClass
        obj.Display();

        // Display message for better readability
        System.out.println("-> Object set to null");

        obj = null;

        // Getting elements in PhantomReference object
        // using standard get() method
        obj = pobj.get();

        // Display status of  objects after fetching
        // PhantomReference class objects
        System.out.println(
            "-> Object status after fetching from PhantomReference now : "
            + obj);

        // Display message only
        System.out.println(
            "-> Calling Display Function after retrieving from weak Object");

        // Try block to check for exceptions
        try {
            obj.Display();
        }

        // Catch block to handle the exceptions
        catch (Exception E) {

            // Print message when an exception occurred
            System.out.println("-> Error : " + E);
        }
    }
}
```

**Output**

```
-> Calling Display Function using strong object:
Display Function invoked ...
-> Object set to null
-> Object status after fetching from PhantomReference now : null
-> Calling Display Function after retrieving from weak Object
-> Error : java.lang.NullPointerException
```

> 因此，可以看出，与软引用和弱引用不同，幻影引用总是返回空值。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate PhantomReference class
// of java.lang.ref package

// Importing Phantomreference and RefereenceQueue classes
// from java.lang.ref package
import java.lang.ref.PhantomReference;
import java.lang.ref.ReferenceQueue;

// Class 1
// HelperClass
class X {

    // Method
    // To print simply
    void show()
    {

        // Display message whenever
        // show() method is called
        System.out.println("show () from X invoked..");
    }
}

// Class 2
// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating default object of X class
        X obj = new X();

        // Creating new reference queue object
        ReferenceQueue<X> rq = new ReferenceQueue<X>();

        // Creating an object of PhantomReference class
        // of X class type with RefereneQueue object
        // reference queue
        PhantomReference<X> phantomobj
            = new PhantomReference<X>(obj, rq);

        // Display message
        System.out.println(
            "-> Trying to retrieve object from Phantom Reference :");

        // Try block to check for exceptions
        try {

            // this will always throw error as it has been
            // collected
            //  by the garbage collector
            phantomobj.get().show();
        }

        // Catch block to handle the exceptions
        catch (Exception e) {

            // Print and display the exception
            System.out.println(e);
        }
    }
}
```

**Output**

```
-> Trying to retrieve object from Phantom Reference :
java.lang.NullPointerException
```