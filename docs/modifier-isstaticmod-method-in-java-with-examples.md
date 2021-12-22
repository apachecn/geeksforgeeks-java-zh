# 修饰符是 Java 中的静态(mod)方法，带有示例

> 原文:[https://www . geesforgeks . org/modifier-isstaticmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isstaticmod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isStatic(mod)** 方法用于检查整数参数是否包含静态修饰符。如果此整数参数表示静态类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```java
public static boolean isStatic(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含静态修饰符，则该方法返回 true 否则为假。

以下程序说明了 isStatic()方法:
**程序 1:**

```java
// Java program to illustrate isStatic() method

import java.lang.reflect.*;

public class GFG {

    // create a String Field
    static String string;

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFG.class
                  .getDeclaredField("string");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is static or not
        boolean result = Modifier.isStatic(mod);

        System.out.println("Mod integer value "
                           + mod + " is static : "
                           + result);
    }
}
```

**Output:**

```java
Mod integer value 8 is static : true

```

**程序 2:**

```java
// Java program to illustrate isStatic()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {

        // get Method class object
        Method[] methods
            = Shape.class.getMethods();

        // get Modifier Integer value
        int mod = methods[0].getModifiers();

        // check Modifier is static or not
        boolean result
            = Modifier.isStatic(mod);

        System.out.println("Mod integer value "
                           + mod + " is static : "
                           + result);
    }

    public static class Shape {

        public static void createShape() {}
    }
}
```

**Output:**

```java
Mod integer value 9 is static : true

```

**参考文献:**T2