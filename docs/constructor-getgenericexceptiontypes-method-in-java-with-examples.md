# Java 中的构造函数 getGenericExceptionTypes()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-getgenericexceptiontypes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getgenericexceptiontypes-method-in-java-with-examples/)

**Java . lang . reflect . constructor 类**的**getGenericExceptionTypes()**方法用于将此构造函数对象上的异常类型作为数组返回。返回的对象数组表示声明由该构造函数对象引发的异常。如果这个构造函数在其 throws 子句中没有声明异常，那么这个方法返回一个长度为 0 的数组。

**语法:**

```
public Type[] getGenericExceptionTypes()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回一个**类型数组**，代表底层可执行文件抛出的异常类型。

**异常:**该方法抛出以下异常:

*   **泛型签名格式错误:**如果泛型方法签名不符合 Java 虚拟机规范中指定的格式。
*   **如果基础可执行文件的 throws 子句引用了不存在的类型声明，则 TypeNotPresentException:** 。
*   **如果基础可执行文件的 throws 子句引用了由于任何原因无法实例化的参数化类型，则出现 malformedparameterzedtypexception:**。

下面的程序说明了 getGenericExceptionTypes()方法:
**程序 1:**

```
// Java program to illustrate
// getGenericExceptionTypes() method

import java.io.IOException;
import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = shape.class;

        // get Constructor object
        // array from class object
        Constructor[] cons
            = classObj.getConstructors();

        // get array of GenericExceptionTypes
        Type[] exceptions
            = cons[0].getGenericExceptionTypes();

        // print length of GenericExceptionTypes array
        System.out.println("GenericExceptions : ");

        for (int i = 0; i < exceptions.length; i++)
            System.out.println(exceptions[i]);
    }

    // demo class
    public class shape {

        public shape() throws IOException,
                              ArithmeticException,
                              ClassCastException
        {
        }
    }
}
```

**Output:**

```
GenericExceptions : 
class java.io.IOException
class java.lang.ArithmeticException
class java.lang.ClassCastException

```

**程序 2:**

```
// Java program to illustrate
// getGenericExceptionTypes() method

import java.lang.reflect.Constructor;
import java.lang.reflect.Type;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons
            = classObj.getConstructors();

        // get array of GenericExceptionTypes
        Type[] exceptions
            = cons[0].getGenericExceptionTypes();

        // print length of GenericExceptionTypes array
        System.out.println(
            "No of Generic Exception thrown : "
            + exceptions.length);
    }
}
```

**Output:**

```
No of Generic Exception thrown : 0

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getGenericExceptionTypes()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getGenericExceptionTypes())