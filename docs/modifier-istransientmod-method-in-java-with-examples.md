# 修饰符是 Java 中的 Transient(mod)方法，带有示例

> 原文:[https://www . geesforgeks . org/modifier-is transientmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-istransientmod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isTransient(mod)** 方法用于检查整数参数是否包含瞬态修饰符。如果此整数参数表示瞬态类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```
public static boolean isTransient(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含瞬态修改器，则该方法返回 true 否则为假。

下面的程序说明了 isTransient()方法:
**程序 1:**

```
// Java program to illustrate isTransient() method

import java.lang.reflect.*;

public class GFG {

    public static transient int number = 1000;

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

        // check Modifier is transient or not
        boolean result
            = Modifier.isTransient(mod);

        System.out.println("Mod integer value "
                           + mod + " is transient : "
                           + result);
    }
}
```

**Output:**

```
Mod integer value 137 is transient : true

```

**程序 2:**

```
// Java program to illustrate isTransient()

import java.io.Serializable;
import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Field class object
        Field field
            = GFGTest
                  .class
                  .getDeclaredField("password");

        // get Modifier Integer value
        int mod = field.getModifiers();

        // check Modifier is transient or not
        boolean result = Modifier.isTransient(mod);

        System.out.println("Mod integer value "
                           + mod
                           + " is transient : "
                           + result);
    }

    // A sample class that uses a transient keyword to
    // skip their serialization.
    class GFGTest implements Serializable {

        // Making password transient for security
        private transient String password;

        // other code
    }
}
```

**Output:**

```
Mod integer value 130 is transient : true

```

**参考文献:**T2