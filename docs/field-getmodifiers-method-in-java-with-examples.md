# Java 中的 Field getModifiers()方法，带示例

> 原文:[https://www . geesforgeks . org/field-get modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getmodifiers-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getModifiers ()** 方法用于将用于字段对象的修饰符作为声明时间作为整数返回。修饰符类应该用于解码修饰符。

**语法:**

```java
public int getModifiers()

```

**参数:**此方法不接受任何东西。

**返回**:这个方法返回底层成员的 Java 语言**修饰符**。

下面的程序说明了 getModifiers()方法:
**程序 1:**

```java
// Java program to illustrate
// getModifiers () method

import java.lang.reflect.Field;
import java.lang.reflect.Modifier;

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

        // apply getModifiers() method
        int modifiers
            = field.getModifiers();

        // print the results
        System.out.println(
            Modifier
                .toString(modifiers));
    }
}
```

**Output:**

```java
private static

```

**程序 2:**

```java
// Java program to illustrate
// getModifiers () method

import java.lang.reflect.Field;
import java.lang.reflect.Modifier;

public class GFG {

    // initialize field
    final static String value
        = "Geeks";

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Field object
        Field field
            = GFG.class
                  .getDeclaredField("value");

        // apply getModifiers() method
        int modifiers
            = field.getModifiers();

        // print the results
        System.out.println(
            Modifier
                .toString(modifiers));
    }
}
```

**Output:**

```java
static final

```

**参考文献:**