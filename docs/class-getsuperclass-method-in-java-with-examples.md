# Java 中的 Class getSuperclass()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getsuperclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getsuperclass-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getSuperclass()** 方法用来获取这个实体的超类。这个实体可以是类、数组、接口等。方法返回该实体的超类。

**语法:**

```
public Class<T> getSuperclass()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回该实体的**超类**。

下面的程序演示了 getSuperclass()方法。

**例 1:**

```
// Java program to demonstrate getSuperclass() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the super class of myClass
        // using getSuperclass() method
        System.out.println("Superclass of myClass: "
                           + myClass.getSuperclass());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Superclass of myClass: class java.lang.Object

```

**例 2:**

```
// Java program to demonstrate getSuperclass() method

public class Test {

    class Arr {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        // returns the Class object for Arr
        Class arrClass = Arr.class;

        // Get the super class of arrClass
        // using getSuperclass() method
        System.out.println("Superclass of arrClass: "
                           + arrClass.getSuperclass());
    }
}
```

**输出:**

```
Superclass of arrClass: class java.lang.Object

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getSuperclass–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getSuperclass--)