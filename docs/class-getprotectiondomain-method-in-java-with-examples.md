# 用示例在 Java 中类 getProtectionDomain()方法

> 原文:[https://www . geeksforgeeks . org/class-getprotectdomain-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getprotectiondomain-method-in-java-with-examples/)

**[Java . lang . class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)**的 **getProtectionDomain()** 方法用于获取该类的 ProtectionDomain。方法以 ProtectionDomain 对象的形式返回此类的指定保护域。

**语法:**

```java
public ProtectionDomain getProtectionDomain()

```

**参数:**该方法不接受任何参数

**返回值:**该方法以 ProtectionDomain 对象的形式返回该类的指定 **ProtectionDomain** 。

**异常**如果安全管理器存在并且其 checkPermission 方法不允许获取 ProtectionDomain，则此方法抛出:

*   **Safety exception** .

下面的程序演示了 getProtectionDomain()方法。

**例 1:**

```java
// Java program to demonstrate
// getProtectionDomain() method

import java.util.*;

public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        try {

            // returns the Class object for this class
            Class myClass = Class.forName("Test");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            // Get the ProtectionDomain of myClass
            // using getProtectionDomain() method
            System.out.println("ProtectionDomain of myClass: "
                               + myClass.getProtectionDomain());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
java.security.AccessControlException: access denied ("java.lang.RuntimePermission" "getProtectionDomain")

```

**例 2:**

```java
// Java program to demonstrate
// getProtectionDomain() method

import java.util.*;

class Main {

    private Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        try {
            // returns the Class object for this class
            Class myClass = Class.forName("Main");

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            String ProtectionDomainName = "obj";

            // Get the ProtectionDomain of myClass
            // using getProtectionDomain() method
            System.out.println("ProtectionDomain of myClass: "
                               + myClass.getProtectionDomain());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
Class represented by myClass: class Main
java.security.AccessControlException: access denied ("java.lang.RuntimePermission" "getProtectionDomain")

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getProtectionDomain–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getProtectionDomain--)