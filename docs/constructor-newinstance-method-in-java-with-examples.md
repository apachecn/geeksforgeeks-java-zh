# Java 中的构造函数 newInstance()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-new instance-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-newinstance-method-in-java-with-examples/)

**构造函数**类的 **newInstance()** 方法用于创建和初始化该构造函数的新实例，初始化参数作为参数传递给该方法。每个参数都被展开以匹配基元形式参数，并且基元和引用参数都根据需要进行方法调用转换。

如果构造函数的形式参数个数为 0，则提供的参数长度为 0 或 null。如果构造函数正常完成，则返回新创建并初始化的实例。

**语法:**

```
public T newInstance(Object... initargs)
  throws InstantiationException, IllegalAccessException,
         IllegalArgumentException, InvocationTargetException

```

**参数:**这个方法接受 **initargs** 作为参数，它是一个对象数组，作为参数传递给构造函数调用。基元类型的值被包装在适当类型的包装对象中(例如，float 中的 Float)。

**返回值:**这个方法返回一个**新对象**，这个对象是通过调用这个对象所代表的构造函数创建的。

**异常:**该方法抛出以下异常:

*   **IllegalAccessException** :如果这个 constructor 对象正在执行 Java 语言访问控制，并且底层的 Constructor 不可访问。
*   **IllegalArgumentException** :如果实际参数和形式参数的个数不同；如果基元参数的展开转换失败；或者，如果在可能的展开之后，参数值不能通过方法调用转换转换为相应的形式参数类型；如果此构造函数属于枚举类型。
*   **instance exception**:如果声明底层构造函数的类代表抽象类。
*   **InvocationTargetException**:如果底层构造函数抛出异常。
*   **exceptioniniinitializerror**:如果这个方法引发的初始化失败。

下面的程序说明了 newInstance()方法:
**程序 1:**

```
// Java program to demonstrate
// Constructor.newInstance() method

import java.lang.reflect.Constructor;
import java.lang.reflect.InvocationTargetException;

public class GFG {

    public static void main(String... args)
        throws InstantiationException,
               IllegalAccessException,
               IllegalArgumentException,
               InvocationTargetException
    {

        // An array of constructor
        Constructor[] constructor
            = Test.class.getConstructors();

        // Apply newInstance method
        Test sampleObject
            = (Test)constructor[0].newInstance();

        System.out.println(sampleObject.value);
    }
}

class Test {

    String value;

    public Test()
    {
        System.out.println("New Instance is created");
        value = "New Instance";
    }
}
```

**输出:**

```
New Instance is created
New Instance

```

**程序 2:**

```
// Java program to demonstrate
// Constructor.newInstance() method

import java.lang.reflect.Constructor;
import java.lang.reflect.InvocationTargetException;

public class GFG {

    public static void main(String... args)
        throws InstantiationException,
               IllegalAccessException,
               IllegalArgumentException,
               InvocationTargetException
    {

        // an array of constructor
        Constructor[] constructor
            = Test.class.getConstructors();

        // apply newInstance method
        Test sampleObject
            = (Test)constructor[0]
                  .newInstance("New Field");

        System.out.println(sampleObject.getField());
    }
}

class Test {

    private String field;

    public Test(String field)
    {
        this.field = field;
    }

    public String getField()
    {
        return field;
    }

    public void setField(String field)
    {
        this.field = field;
    }
}
```

**输出:**

```
New Field

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # new instance(Java . lang . object…)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#newInstance(java.lang.Object...))