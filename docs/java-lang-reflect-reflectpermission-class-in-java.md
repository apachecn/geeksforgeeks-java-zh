# java 中的 Java . lang . reflect . reflect permission 类

> 原文:[https://www . geesforgeks . org/Java-lang-reflect-reflection permission-class-in-Java/](https://www.geeksforgeeks.org/java-lang-reflect-reflectpermission-class-in-java/)

ReflectPermission 类扩展了 BasicPermission 类。这是一个“命名”权限，即它包含一个名称，但不包含任何操作。如果需要，它可以在基本权限之上实现操作。它用于获取关于构造函数行为的信息。

<figure class="table">

| **constructor** | **Description** |
| --- | --- |
| ReflectPermission(字符串名称) | Used to create a reflect permission with the specified name. |
| ReflectPermission (string name, string action) | Used to create a reflect permission with the specified name and action. |

</figure>

**方法继承自 java.security.BasicPermission 类:**

<figure class="table">

| **Method** | **Description** |
| --- | --- |
| 等于(对象对象) | It checks whether two BasicPermission objects are equal. |
| 【定语】 | It returns the operation in a string format, which is currently an empty string because there is no operation in ReflectPermission. |
| hashCode() | It returns the hash code value of this object. |
| 隐含(许可权限) | Check whether the given permission is implied by the object. |
| 新权限集合() | It returns a new PermissionCollection object. |

</figure>

下面是给定类的示例/用法:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Use of java.lang.reflect.ReflectPermission Class in Java
import java.lang.reflect.ReflectPermission;
class GFG {
    public static void main(String[] args)
    {
        if (canAccessPrivateMethods()) {
            System.out.println("Permission granted");
        }
        else {
            System.out.println("Permission not granted");
        }
    }
    static boolean canAccessPrivateMethods()
    {
        try {
            SecurityManager securityManager
                = System.getSecurityManager();
            if (null != securityManager) {
                securityManager.checkPermission(
                    new ReflectPermission(
                        "suppressAccessChecks"));
            }
        }
        catch (SecurityException e) {
            return false;
        }
        return true;
    }
}
```

**Output**

```java
Permission not granted
```