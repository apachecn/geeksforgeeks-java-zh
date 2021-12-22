# Java 中的类 getDeclaredMethods()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getdeclaredmethods-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getdeclaredmethods-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getDeclaredMethods()** 方法用于获取该类的方法，这些方法是私有的、公共的、受保护的或默认的方法及其成员或其成员类和接口的成员，而不是继承的方法。方法以方法对象数组的形式返回此类的方法。

**语法:**

```
public Method[] getDeclaredMethods()
               throws SecurityException

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法以 method 对象数组的形式返回这个类的**方法**。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getDeclaredMethods()方法。

**例 1:**

```
// Java program to demonstrate getDeclaredMethods() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the methods of myClass
        // using getDeclaredMethods() method
        System.out.println(
            "DeclaredMethods of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredMethods()));
    }
}
```

**Output:**

> 由 myClass 表示的类:class Test
> declared methods of my class:[public static void Test . main(Java . lang . string[])抛出 Java . lang . class notfoundexception]

**例 2:**

```
// Java program to demonstrate getDeclaredMethods() method

import java.util.*;

class Main {

    public Object obj;

    private void function() {}

    Main()
    {

        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for this class
        Class myClass = Class.forName("Main");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the methods of myClass
        // using getDeclaredMethods() method
        System.out.println(
            "DeclaredMethods of myClass: "
            + Arrays.toString(
                  myClass.getDeclaredMethods()));
    }
}
```

**Output:**

> 由 myClass 表示的类:class Main
> 声明 myClass 的方法:【公共静态 void Main . Main(Java . lang . string[])抛出 Java . lang . class notfoundexception，私有 void Main.function()】

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getDeclaredMethods–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getDeclaredMethods--)