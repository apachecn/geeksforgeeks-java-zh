# 如何解决 Java 中的类强制转换异常？

> 原文:[https://www . geesforgeks . org/如何在 java 中解决类转换异常/](https://www.geeksforgeeks.org/how-to-solve-class-cast-exceptions-in-java/)

扰乱程序正常流程的未被接受的、不想要的事件称为[](https://www.geeksforgeeks.org/exceptions-in-java/)**异常。大多数时候异常是由我们的程序引起的，这些是可以恢复的。例如:如果我们的程序要求从位于美国的远程文件中读取数据。在运行时，如果远程文件不可用，那么我们将得到一个运行时异常，表示文件未找到异常。如果出现 fileNotFoundException，我们可以向程序提供本地文件，以便正常读取和继续程序的其余部分。**

**java 中主要有两种异常类型，如下所示:**

****1。检查异常:**编译器在运行时为程序的顺利执行而检查的异常称为检查异常。在我们的程序中，如果有机会出现检查异常，那么我们应该强制处理该检查异常(通过 try-catch 或 throws 关键字)，否则我们将得到一个编译时错误。**

**检查异常的例子有 **classNotFoundException、IOException、SQLException 等。****

****2。未检查异常:**未被编译器检查的异常，无论程序员是否处理这种类型的异常，都被称为未检查异常。**

**未检查异常的例子有**算术异常、数组异常等。****

**是否检查异常只有在编译时不可能出现任何异常时，每个异常才会在运行时出现。**

****ClassCastException:** 它是 RuntimeException 的子类，因此它是一个未检查的异常。每当我们试图不正确地将一个类从一种类型类型转换为另一种类型类型时，即当我们试图将父对象类型转换为子类型类型时，或者当我们试图将一个对象类型转换为它不是其实例的子类时，JVM 会自动产生这个异常。**

**在下面的程序中，我们创建了一个 object 类型的对象，并将该对象类型转换为 String 对象。我们知道 Object 类是 java 中所有类的父类，当我们试图将父对象类型转换为它的子类型时，我们最终得到了 java.lang.ClassCastException**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// import required packages
import java.io.*;
import java.lang.*;
import java.util.*;
// driver class
class geeks {

    // main method
    public static void main(String[] args)
    {
        try {

            // creating an object
            Object o = new Object();

            // type casting the object o to string which
            // give the classcasted exception because we
            // type cast an parent type to its child type.
            String s = (String)o;

            System.out.println(s);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****Output**

```
java.lang.ClassCastException: class java.lang.Object cannot be cast to class java.lang.String (java.lang.Object and java.lang.String are in module java.base of loader 'bootstrap')
```** 

**为了处理 ClassCastException，请注意，当您试图将一个类的对象类型转换为另一个类时，请确保新类型属于其父类之一，或者不要试图将父对象类型转换为其子类型。在使用集合时，我们可以通过使用泛型来防止 ClassCastException，因为泛型提供了编译时检查。**

**下面是问题陈述的实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// import required packages
import java.io.*;
import java.lang.*;
import java.util.*;

// driver class
class geeks {

    // main method
    public static void main(String[] args)
    {
        try {

            // creating an object
            String s = "GFG";
            Object o = (Object)s;

            // Object class is parent class of every class
            // Hence exception doesn't occur.
            System.out.println(o);
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

****Output**

```
GFG
```**