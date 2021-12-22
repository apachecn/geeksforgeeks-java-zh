# Java 中的 Field getGenericType()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getgenerictype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getgenerictype-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getGenericType()** 方法，用于返回表示该 Field 对象的声明类型的类型对象。返回的类型对象可以是类型的子接口的实现之一:泛型类型、参数化类型、通配符类型、类型变量、类。如果“字段类型”对象是参数化类型，则返回的“类型”对象必须准确反映源代码中使用的实际类型参数，如果基础字段的类型是类型变量或参数化类型，则创建它。否则，就解决了。

**语法:**

```
public Type getGenericType()

```

**参数:**此方法不接受任何东西。

**返回**:该方法返回一个**类型**对象，该对象代表该字段对象所代表的字段的声明类型。

**异常**:该方法返回以下异常:

*   **泛型签名格式错误:**如果泛型字段签名不符合 Java 虚拟机规范中指定的格式。
*   **如果基础字段的泛型类型签名引用了不存在的类型声明，则 TypeNotPresentException:** 。
*   **如果基础字段的泛型签名引用了由于任何原因无法实例化的参数化类型，则出现 malformedparameterzedtypexception:**。

下面的程序说明了 getGenericType()方法:
**程序 1:**

```
// Java program to illustrate
// getGenericType() method

import java.lang.reflect.Field;
import java.lang.reflect.Type;

public class GFG {

    // initialize field
    private static int number;

    public static void main(String[] args)
        throws NoSuchFieldException
    {
        // get Field object
        Field field
            = GFG.class
                  .getDeclaredField("number");

        // apply getGenericType() method
        Type type = field.getGenericType();

        // print Results
        System.out.println(
            "Type class: "
            + type.getClass());
        System.out.println(
            "Type name: "
            + type.getTypeName());
    }
}
```

**Output:**

```
Type class: class java.lang.Class
Type name: int

```

**程序 2:**

```
// Java program to illustrate
// getGenericType() method

import java.lang.reflect.Field;
import java.lang.reflect.Type;

public class GFG {

    // initialize field
    final static String value = "Geeks";

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Field object
        Field field
            = GFG.class
                  .getDeclaredField("value");

        // apply getGenericType() method
        Type type = field.getGenericType();

        // print Results
        System.out.println(
            "Type class: "
            + type.getClass());
        System.out.println(
            "Type name: "
            + type.getTypeName());
    }
}
```

**Output:**

```
Type class: class java.lang.Class
Type name: java.lang.String

```

**参考文献:**