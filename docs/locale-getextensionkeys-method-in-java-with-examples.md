# Java 中的 Locale getExtensionKeys()方法，示例

> 原文:[https://www . geesforgeks . org/locale-getextensionkeys-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-getextensionkeys-method-in-java-with-examples/)

Java 中 **[Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的 **getExtensionKeys()** 方法用来返回一组与这个 Locale 相关联的扩展键，这些扩展键不能被修改，并且键保持小写。如果没有扩展名，则该方法返回一个空集合。

**语法:**

```java
public Set <Character> getExtensionKeys()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回一组与该区域设置相关联的扩展键，如果没有扩展，则返回一个空集。

以下程序说明了 getExtensionKeys()方法的工作:
**程序 1:**

```java
// Java code to illustrate
// getExtensionKeys() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("th", "TH", "TH");

        // Displaying first locale
        System.out.println("Locale: "
                           + first_locale);

        // Displaying the set
        System.out.println("The KeySet: "
                           + first_locale.getExtensionKeys());
    }
}
```

**Output:**

```java
Locale: th_TH_TH_#u-nu-thai
The KeySet: [u]

```

**程序 2:**

```java
// Java code to illustrate
// getExtensionKeys() method

import java.util.*;

public class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "US");

        // Displaying first locale
        System.out.println("Locale: "
                           + first_locale);

        // Displaying the set
        System.out.println("The KeySet: "
                           + first_locale.getExtensionKeys());
    }
}
```

**Output:**

```java
Locale: en_US
The KeySet: []

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/locale . html # getExtensionKeys()](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html#getExtensionKeys())