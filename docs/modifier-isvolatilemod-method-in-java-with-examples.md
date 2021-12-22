# 修饰符是 Java 中的一个简单(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-isvolatilemd-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isvolatilemod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isVolatile(mod)** 方法用于检查整数参数是否包含 Volatile 修饰符。如果此整数参数表示可变类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```
public static boolean isVolatile(int mod)

```

**参数:**该方法接受整数 mod 作为参数，表示一组修饰符。

**返回**:如果 mod 包含 volatile 修饰符，则该方法返回 true 否则为假。

以下程序说明 isVolatile()方法:
**程序 1:**

```
// Java program to illustrate isVolatile() method

import java.lang.reflect.*;

public class GFG {

    volatile static String field1 = "GeeksForGeeks";

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFG
                  .class
                  .getDeclaredField("field1");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is volatile or not
        boolean result
            = Modifier.isVolatile(mod);

        System.out.println("Mod integer value "
                           + mod
                           + " is volatile : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 72 is volatile : true

```

**程序 2:**

```
// Java program to illustrate isVolatile()

import java.lang.reflect.*;

public class GFG {

    volatile Long number
        = 139892824314253L;

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFG
                  .class
                  .getDeclaredField("number");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is volatile or not
        boolean result
            = Modifier.isVolatile(mod);

        System.out.println("Mod integer value "
                           + mod
                           + " is volatile : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 64 is volatile : true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # isVolatile(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isVolatile(int))