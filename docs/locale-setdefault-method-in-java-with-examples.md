# Java 中的 Locale setDefault()方法，示例

> 原文:[https://www . geesforgeks . org/locale-set default-method-in-Java-with-examples/](https://www.geeksforgeeks.org/locale-setdefault-method-in-java-with-examples/)

Java 中 **[Locale 类](https://www.geeksforgeeks.org/java-util-locale-class-java-set-1/)** 的 **setDefault(Locale newLoc)** 方法用于设置 JVM 或 Java 虚拟机的这个实例的默认区域设置，这丝毫不会影响主机区域设置。

**语法:**

```
public static void setDefault(Locale newLoc)
```

**参数:**该方法采用一个区域设置类型的参数**纽洛克**，这是指要设置的新默认区域设置。

**返回值:**该方法不返回值。

**异常:**该方法可以抛出如下异常-

*   如果安全管理器存在并且其 checkPermission 方法不允许该操作，则会引发 SecurityException。
*   如果 newloc 为 null，将引发的 nullpointexception

下面的程序说明了区域设置类的 setDefault()方法:
**示例 1:**

```
// Java code to illustrate hashCode() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("nu", "NO", "NY");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(new Locale("ar", "SA"));

        Locale new_locale = Locale.getDefault();

        // Displaying the hash_code of new locale
        System.out.println("The Hash Code: "
                           + new_locale);
    }
}
```

**Output:**

```
First Locale: nu_NO_NY
The Hash Code: ar_SA

```

**例 2:**

```
// Java code to illustrate hashCode() method

import java.util.*;

class Locale_Demo {
    public static void main(String[] args)
    {

        // Creating a new locale
        Locale first_locale
            = new Locale("en", "In");

        // Displaying first locale
        System.out.println("First Locale: "
                           + first_locale);

        // Setting the Locale
        Locale.setDefault(new Locale("en", "GB"));

        Locale new_locale = Locale.getDefault();

        // Displaying the hash_code of new locale
        System.out.println("The Hash Code: "
                           + new_locale);
    }
}
```

**Output:**

```
First Locale: en_IN
The Hash Code: en_GB

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/util/locale . html # setdefault(Java . util . locale)](https://docs.oracle.com/javase/7/docs/api/java/util/Locale.html#setDefault(java.util.Locale))