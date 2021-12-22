# Java 中的构造函数 getGenericParameterTypes()方法，示例

> 原文:[https://www . geesforgeks . org/constructor-getgenericparametertypes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getgenericparametertypes-method-in-java-with-examples/)

**Java . lang . reflect . constructor 类**的**getGenericParameterTypes()**方法用于返回一个对象数组，该数组表示该构造函数对象上存在的参数类型。此方法返回的数组的排列顺序与此构造函数对象上的参数顺序相同。如果构造函数没有参数，则该方法返回长度为 0 的数组。

**语法:**

```
public Type[] getGenericParameterTypes()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法按照声明顺序返回一个**类型数组**，代表底层可执行文件的形式参数类型。

**异常:**该方法抛出以下异常:

*   **泛型签名格式错误:**如果泛型方法签名不符合 Java 虚拟机规范中指定的格式。
*   **如果基础可执行文件的 throws 子句引用了不存在的类型声明，则 TypeNotPresentException:** 。
*   **如果基础可执行文件的 throws 子句引用了由于任何原因无法实例化的参数化类型，则出现 malformedparameterzedtypexception:**。

下面的程序说明了 getGenericParameterTypes()方法:
**程序 1:**

```
// Java program to illustrate
// getGenericParameterTypes() method

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

        // get array of GenericParameterTypes
        Type[] parameters
            = cons[0].getGenericParameterTypes();

        // print length of GenericParameterTypes array
        System.out.println("Parameters : ");

        for (int i = 0; i < parameters.length; i++)
            System.out.println(parameters[i]);
    }

    // demo class
    public class shape {

        public shape(int a, long b, double c)
        {
        }
    }
}
```

**Output:**

```
Parameters : 
class GFG
int
long
double

```

**程序 2:**

```
// Java program to illustrate
// getGenericParameterTypes() method

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

        // get array of GenericParameterTypes
        Type[] params
            = cons[0].getGenericParameterTypes();

        // print length of GenericParameterTypes array
        System.out.println("No of Parameters: "
                           + params.length);
    }
}
```

**Output:**

```
No of Parameters: 3

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getGenericParameterTypes()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getGenericParameterTypes())