# 场所。Java 中的 FilteringMode values()方法，示例

> 原文:[https://www . geesforgeks . org/locale-filtering mode-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-filteringmode-values-method-in-java-with-examples/)

java 中**[Java . util](https://www.geeksforgeeks.org/java-util-package-java/). Locale . filtering mode enum**的 **values()** 方法用于获取该 Locale 常量的值。FilteringMode 枚举类型，按照它们的声明顺序。这个方法返回一个常量数组，因此也可以迭代。

**语法:**

```java
public static Locale.FilteringMode[] values()

```

**参数:**此方法不接受任何参数。

**返回类型:**这个方法返回一个这个区域的常量的**数组**。FilteringMode 枚举类型。

**异常:**这个方法不抛出任何异常。

**程序 1:**

```java
// Java program to demonstrate
// the above method

import java.util.*;
import java.util.Locale.*;

public class LocaleFilteringModeDemo {
    public static void main(String[] args)
    {

        // Getting the array of constants
        // of Locale.FilteringMode
        System.out.println("Array of constants: "
                           + Arrays
                                 .toString(
                                     Locale.FilteringMode
                                         .values()));
    }
}
```

**输出:**

> 常量数组:【AUTOSELECT _ FILTERING，EXTENDED _ FILTERING，IGNORE_EXTENDED_RANGES，MAP_EXTENDED_RANGES，REJECT _ EXTENDED _ RANGES】

**参考:**[https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html #值–](https://docs.oracle.com/javase/9/docs/api/java/util/Locale.FilteringMode.html#values--)