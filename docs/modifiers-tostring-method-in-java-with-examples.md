# Java 中的修饰符 toString()方法，示例

> 原文:[https://www . geesforgeks . org/modifiers-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-tostring-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **toString()** 方法用于获取一个字符串，该字符串表示指定修饰符中的访问修饰符标志。

**语法:**

```
public static String toString(int mod)

```

**参数:**该方法接受一个参数 **mod** ，代表一组修改器。

**返回**:这个方法返回一个由 mod 表示的修改器集合的**字符串表示**。

下面的程序说明了 toString()方法:
**程序 1:**

```
// Java program to illustrate
// toString() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier value
        // of String class
        int result
            = String.class.getModifiers();

        // apply toString() methods
        System.out.println(
            "Modifiers: "
            + Modifier.toString(result));
    }
}
```

**Output:**

```
Modifiers: public final

```

**程序 2:**

```
// Java program to illustrate toString()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // printing the Modifiers name
        // between integer value 10 to 20

        for (int i = 10; i < 20; i++) {

            // apply toString() methods
            System.out.println(
                "i: "
                + i + " Modifier:"
                + Modifier.toString(i));
        }
    }
}
```

**Output:**

```
i: 10 Modifier:private static
i: 11 Modifier:public private static
i: 12 Modifier:protected static
i: 13 Modifier:public protected static
i: 14 Modifier:protected private static
i: 15 Modifier:public protected private static
i: 16 Modifier:final
i: 17 Modifier:public final
i: 18 Modifier:private final
i: 19 Modifier:public private final

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#toString--)