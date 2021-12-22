# Java 中的可克隆接口

> 原文:[https://www.geeksforgeeks.org/cloneable-interface-in-java/](https://www.geeksforgeeks.org/cloneable-interface-in-java/)

**Java.lang.Cloneable** 接口是一个[标记接口](https://www.geeksforgeeks.org/marker-interface-java/)。它是在 JDK 1.0 中引入的。对象类中有一个方法[克隆()](https://www.geeksforgeeks.org/clone-method-in-java-2/)。**可克隆**接口由一个类实现，以使 [Object.clone()](https://www.geeksforgeeks.org/clone-method-in-java-2/) 方法有效，从而进行逐字段复制。该接口允许实现类克隆其对象，而不是使用**新的**运算符。

**申报**T0】

**示例 1:** 下面的程序解释说，如果你试图克隆一个没有实现可克隆接口的对象，它将会**克隆一个支持异常**，你可能想要处理这个异常。

## Java

```
// Java program to Demonstrate the
// application of Cloneable interface

import java.io.*;
import java.util.*;

class Student {

    // attributes of Student class
    String name = null;
    int id = 0;

    // default constructor
    Student() {}

    // parameterized constructor
    Student(String name, int id)
    {
        this.name = name;
        this.id = id;
    }

    public static void main(String[] args)
    {
        // create an instance of Student
        Student s1 = new Student("Ashish", 121);

        // Try to clone s1 and assign
        // the new object to s2
        Student s2 = s1.clone();
    }
}
```

**输出:**

```
prog.java:28: error: incompatible types: Object cannot be converted to Student
        Student s2 = s1.clone();
                             ^
1 error

```

**示例 2:** 下面的代码解释了如何正确使用可克隆接口来使 Object.clone()方法合法。实现此接口的类应该重写 Object.clone()方法(受保护)，以便可以调用它。

## Java

```
// Java program to illustrate Cloneable interface
import java.lang.Cloneable;

// By implementing Cloneable interface
// we make sure that instances of class A
// can be cloned.
class A implements Cloneable {
    int i;
    String s;

    // A class constructor
    public A(int i, String s)
    {
        this.i = i;
        this.s = s;
    }

    // Overriding clone() method
    // by simply calling Object class
    // clone() method.
    @Override
    protected Object clone()
        throws CloneNotSupportedException
    {
        return super.clone();
    }
}

public class Test {
    public static void main(String[] args)
        throws CloneNotSupportedException
    {
        A a = new A(20, "GeeksForGeeks");

        // cloning 'a' and holding
        // new cloned object reference in b

        // down-casting as clone() return type is Object
        A b = (A)a.clone();

        System.out.println(b.i);
        System.out.println(b.s);
    }
}
```

**输出**

```
20
GeeksForGeeks
```

### 使用克隆()方法进行深度拷贝

**深度对象克隆**就像通过将字段从原始对象复制到克隆对象来创建原始对象的精确副本。为复制原始对象内容的克隆对象分配单独的内存。[克隆()](https://www.geeksforgeeks.org/clone-method-in-java-2/)方法可以在实现的基础上创建原始对象的浅层副本和**深层副本**。深度复制会创建一个内容与原始对象相同的新内存。这就是为什么当我们在克隆后更改原始对象的内容时，这些更改不会反映在克隆对象中。副本有[深、浅](https://www.geeksforgeeks.org/deep-shallow-lazy-copy-java-examples/)、[和](https://www.geeksforgeeks.org/deep-shallow-lazy-copy-java-examples/)等类型。下面的代码解释了使用 clone()方法的深度复制。

## Java

```
// A Java program to demonstrate deep copy
// using clone()
import java.util.ArrayList;

// An object reference of this class is
// contained by Test2
class Test {
    int x, y;
}

// Contains a reference of Test and implements
// clone with deep copy.
class Test2 implements Cloneable {
    int a, b;

    Test c = new Test();

    public Object clone() throws CloneNotSupportedException
    {
        // Assign the shallow copy to new reference variable
        // t
        Test2 t = (Test2)super.clone();

        t.c = new Test();

        // Create a new object for the field c
        // and assign it to shallow copy obtained,
        // to make it a deep copy
        return t;
    }
}

public class Main {
    public static void main(String args[])
        throws CloneNotSupportedException
    {
        Test2 t1 = new Test2();
        t1.a = 10;
        t1.b = 20;
        t1.c.x = 30;
        t1.c.y = 40;

        Test2 t3 = (Test2)t1.clone();
        t3.a = 100;

        // Change in primitive type of t2 will not
        // be reflected in t1 field
        t3.c.x = 300;

        // Change in object type field of t2 will not
        // be reflected in t1(deep copy)
        System.out.println(t1.a + " " + t1.b + " " + t1.c.x
                           + " " + t1.c.y);
        System.out.println(t3.a + " " + t3.b + " " + t3.c.x
                           + " " + t3.c.y);
    }
}
```

**输出**

```
10 20 30 40
100 20 300 0
```

**注意:**此界面不包含克隆方法。因此，不可能仅仅因为一个对象实现了这个接口就克隆它。即使反射性地调用克隆方法，也不能保证它会成功。

**参考:**[https://docs . Oracle . com/en/Java/javase/11/docs/API/Java . base/Java/lang/cloneable . html](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/Cloneable.html)