# 修饰符是 Java 中的 Public(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-ispublicmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-ispublicmod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的**是 Public(mod)** 方法，用于检查整数参数是否包含 Public 修饰符。如果此整数参数表示公共类型修饰符，则方法返回 true 否则返回 false。

**语法:**

```
public static boolean isPublic(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含公共修饰符，则该方法返回 true 否则为假。

以下程序说明 isPublic()方法:
**程序 1:**

```
// Java program to illustrate isPublic() method

import java.lang.reflect.*;

public class GFG {

    // create a String Field
    public String string;

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFG.class.getDeclaredField("string");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is public or not
        boolean result = Modifier.isPublic(mod);

        System.out.println("Mod integer value "
                           + mod + " is public : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 1 is public : true

```

**程序 2:**

```
// Java program to illustrate isPublic()

import java.lang.reflect.*;

public class GFG {

    // create an int Field
    public int numbers;

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFG.class
                  .getDeclaredField("numbers");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is public or not
        boolean result = Modifier.isPublic(mod);

        System.out.println("Mod integer value "
                           + mod + " is public : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 1 is public : true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # isPublic(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isPublic(int))