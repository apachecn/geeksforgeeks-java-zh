# Java 中的 Locale getDefault()方法

> 原文:[https://www . geesforgeks . org/locale-get default-method-in-Java/](https://www.geeksforgeeks.org/locale-getdefault-method-in-java/)

### getDefault（）

此方法返回由 Java 虚拟机设置的默认区域设置。这是静态方法，因此可以在不创建 Locale 类的对象的情况下调用它。

**语法:**

```java
public static Locale getDefault()
```

**返回值:**该方法返回 Java 虚拟机设置的默认区域设置。

下面是说明 getDefault()方法的代码:

**程序 1:**

```java
// Java code to demonstrate
// getLocale() method in Locale

import java.util.Locale;
public class GfG {

    // main method
    public static void main(String[] args)
    {
        // declaring object of Locale
        Locale locale;

        // calling the getDefault method
        locale = Locale.getDefault();

        // printing the locale
        System.out.println(locale);
    }
}
```

**Output:**

```java
en_US

```

### getDefault（Locale.Category category）

此方法返回由 Java 虚拟机为指定类别设置的默认区域设置。这是静态方法，因此可以在不创建 Locale 类的对象的情况下调用它。

**语法:**

```java
Locale.getDefault(Locale.Category category)
```

**参数:**取 Locale.Category 类型的强制参数**类别**。

**返回值:**对于指定的类别，该方法返回类型为 Locale 的默认 Locale 集。

**异常:**如果参数中传递的类别为空，getDefault()方法将抛出 **NullPointerException** 。

下面是说明 getDefault(Locale)的代码。类别类别):

**程序 1:**

```java
// Java code to demonstrate
// getLocale() method in Locale

import java.util.Locale;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // declaring object of Locale
        Locale locale;

        // Specified category.
        Locale.Category category = Locale.Category.DISPLAY;

        // calling the getDefault method
        locale = Locale.getDefault(category);

        // printing the locale
        System.out.println(locale);
    }
}
```

**Output:**

```java
en_US

```

**程序 2:** 演示空指针异常

```java
// Java code to demonstrate
// getLocale() method in Locale

import java.util.*;

public class GfG {

    // main method
    public static void main(String[] args)
    {
        // declaring object of Locale
        Locale locale;

        try {
            // Specified category = null
            Locale.Category category = null;

            // calling the getDefault method
            // This will throw exception
            // as the category passed is null
            locale = Locale.getDefault(category);

            // printing the locale
            System.out.println(locale);
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Exception: java.lang.NullPointerException

```