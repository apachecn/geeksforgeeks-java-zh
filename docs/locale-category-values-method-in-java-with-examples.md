# 场所。Java 中的类别值()方法，示例

> 原文:[https://www . geesforgeks . org/locale-category-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-category-values-method-in-java-with-examples/)

java 中**[Java . util](https://www.geeksforgeeks.org/java-util-package-java/). Locale . category enum**的 **values()** 方法用于获取该 Locale 常量的值。类别枚举类型，按照它们的声明顺序。这个方法返回一个常量数组，因此也可以迭代。

**语法:**

```java
public static Locale.Category[] values()

```

**参数:**此方法不接受任何参数。

**返回类型:**这个方法返回一个这个区域的常量的**数组**。类别枚举类型。

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

        // Getting the array of constants
        // of Locale.Category
        System.out.println("Array of constants: "
                           + Arrays.toString(
                                 Locale.Category
                                     .values()));
    }
}
```

**输出:**

```java
Array of constants: [DISPLAY, FORMAT]

```

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.category . html # values–](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.Category.html#values--)