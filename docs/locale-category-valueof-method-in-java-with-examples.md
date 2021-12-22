# 场所。Java 中的类别值()方法，示例

> 原文:[https://www . geesforgeks . org/locale-category-value of-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-category-valueof-method-in-java-with-examples/)

java 中**[Java . util](https://www.geeksforgeeks.org/java-util-package-java/). Locale . category enum**的 **valueOf()** 方法用于获取该 Locale 指定常量的值。类别枚举类型。此方法将常量名称作为参数。

**语法:**

```java
public static Locale.Category valueOf(String name)

```

**参数:**该方法接受一个参数**名称**，这是一个常量名称，其值将从 Locale 中检索。类别枚举。

**返回类型:**这个方法返回这个**区域设置的一个实例。类别**枚举类型具有指定名称的值。

**异常:**这个方法不抛出任何异常。

**程序 1:**

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleCategoryDemo {
    public static void main(String[] args)
    {

        String name = "DISPLAY";

        // Getting the constant
        // of Locale.Category
        System.out.println("Locale.Category "
                           + "value of "
                           + name + ": "
                           + Locale.Category
                                 .valueOf(name));
    }
}
```

**输出:**

```java
Locale.Category value of DISPLAY: DISPLAY

```

**程序二:**

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleCategoryDemo {
    public static void main(String[] args)
    {

        String name = "FORMAT";

        // Getting the constant
        // of Locale.Category
        System.out.println("Locale.Category "
                           + "value of "
                           + name + ": "
                           + Locale.Category
                                 .valueOf(name));
    }
}
```

**输出:**

```java
Locale.Category value of FORMAT: FORMAT

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.category . html # value of-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#valueOf-java.lang.String-)