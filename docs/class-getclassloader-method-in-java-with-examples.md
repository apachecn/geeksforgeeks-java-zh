# Java 中的 Class getClassLoader()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getclass loader-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getclassloader-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getClassLoader()** 方法用于获取该实体的 ClassLoader。这个实体可以是类、数组、接口等。方法返回该实体的类加载器。

**语法:**

```
public ClassLoader getClassLoader()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回实体的**类加载器**。

下面的程序演示了 getClassLoader()方法。

**例 1:**

```
// Java program to demonstrate getClassLoader() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the classLoader of myClass
        // using getClassLoader() method
        System.out.println("ClassLoader of myClass: "
                           + myClass.getClassLoader());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
ClassLoader of myClass: sun.misc.Launcher$AppClassLoader@42a57993

```

**例 2:**

```
// Java program to demonstrate getClassLoader() method

public class Test {

    class Arr {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for Arr
        Class arrClass = Arr.class;

        // Get the classLoader of arrClass
        // using getClassLoader() method
        System.out.println("ClassLoader of arrClass: "
                           + arrClass.getClassLoader());
    }
}
```

**输出:**

```
ClassLoader of arrClass: sun.misc.Launcher$AppClassLoader@42a57993

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getclass loader–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getClassLoader--)