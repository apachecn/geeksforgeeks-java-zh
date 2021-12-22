# Java 中的类 getName()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getname-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getName()** 方法用于获取该实体的名称。这个实体可以是类、数组、接口等。方法以字符串形式返回实体的名称。

**语法:**

```
public String getName()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法将实体的**名称**作为字符串返回。

下面的程序演示了 getName()方法。

**例 1:**

```
// Java program to demonstrate getName() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the name of myClass
        // using getName() method
        System.out.println("Name of myClass: "
                           + myClass.getName());
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Name of myClass: Test

```

**例 2:**

```
// Java program to demonstrate getName() method

public class Test {

    class Arr {
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for A
        Class arrClass = Arr.class;

        // Get the name of arrClass
        // using getName() method
        System.out.println("Name of arrClass: "
                           + arrClass.getName());
    }
}
```

**输出:**

```
Name of arrClass: Test$Arr

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getName–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getName--)