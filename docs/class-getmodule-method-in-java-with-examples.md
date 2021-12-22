# Java 中的类 getModule()方法，带示例

> 原文:[https://www . geesforgeks . org/class-get module-in-Java-method-with-examples/](https://www.geeksforgeeks.org/class-getmodule-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getModule()** 方法用于获取该实体的模块。这个实体可以是类、数组、接口等。方法返回实体的模块。

**语法:**

```
public Module getModule()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回实体的**模块**。

下面的程序演示了 getModule()方法。

**注意:**这个方法是 Java 9 中引入的。因此，要运行这个方法，我们需要一个 Java 9 编译器。所以这不会在在线 IDE 中运行。

**例 1:**

```
// Java program to demonstrate getModule() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the module of myClass
        // using getModule() method
        System.out.println("Module of myClass: "
                           + myClass.getModule());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Module of myClass: unnamed module @23fc625e

```

**例 2:**

```
// Java program to demonstrate getModule() method

public class Test {

    class Arr {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for Arr
        Class arrClass = Arr.class;

        // Get the module of arrClass
        // using getModule() method
        System.out.println("Module of arrClass: "
                           + arrClass.getModule());
    }
}
```

**输出:**

```
Module of arrClass: unnamed module @23fc625e

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getModule–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getModule--)