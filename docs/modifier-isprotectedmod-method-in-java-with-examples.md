# 修饰符是 Java 中受保护的(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-is protectedmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isprotectedmod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isProtected(mod)** 方法用于检查整数参数是否包含受保护的修饰符。如果此整数参数表示受保护的类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```
public static boolean isProtected(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含受保护的修改器，则该方法返回 true 否则为假。

下面的程序说明了 isProtected()方法:
**程序 1:**

```
// Java program to illustrate isProtected() method

import java.lang.reflect.*;

public class GFG {

    // create a String Field
    protected String string;

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

        // check Modifier is protected or not
        boolean result = Modifier.isProtected(mod);

        System.out.println("Mod integer value "
                           + mod + " is protected : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 4 is protected : true

```

**程序 2:**

```
// Java program to illustrate isProtected()

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
            = GFG.class.getDeclaredField("numbers");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is protected or not
        boolean result
            = Modifier.isProtected(mod);

        System.out.println("Mod integer value "
                           + mod + " is protected : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 1 is protected : false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # is protected(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isProtected(int))