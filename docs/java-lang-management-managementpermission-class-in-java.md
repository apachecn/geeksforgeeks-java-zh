# java 中的 Java . lang . management . managementpermission 类

> 原文:[https://www . geesforgeks . org/Java-lang-management-management permission-class-in-Java/](https://www.geeksforgeeks.org/java-lang-management-managementpermission-class-in-java/)

java.lang.ManagementPermission 类包含确定对系统资源的访问的抽象方法。每个物体都有名字。大多数权限对象也有一些相关联的“动作”，告诉这个权限对象允许哪些活动。

**类申报:**

```java
public final class ManagementPermission
extends BasicPermission
```

**施工方:**

```java
Permission(String name)
```

**公共权限(字符串名称):**使用此名称构造新的权限对象。

**方法:**

<figure class="table">

| way | describe |
| --- | --- |
| 检查防护(对象对象) | Used to determine whether the Permission object can be protected (protect access to another object). |
| Equal to (object object) | Check whether two permission objects are equal. |
| hashCode() | It returns the hash value of this Permission object. |
| 获取名（） | 返回该权限的名称。 |
| Implicit (permission permission) | Check whether this ManagementPermssion object implies this permission. |
| 新权限集合() | It returns a new PermissionCollection object. |
| toString() | It returns the string representation of the specified Permission object. |

</figure>

**1 . public void checkGuard(Object Object)**:用于判断该 Permission 对象是否可以被保护(保护对另一个对象的访问)。

```java
Parameters:
object - the object to guard.
Throws:
SecurityException - if the access is denied by checkPermission method.
```

**2 .公共抽象布尔隐含(Permission permission):** 检查这个 ManagementPermssion 对象是否隐含这个权限。

```java
Parameters:
permission - the permission to check against.
Returns:
true if this permission is implied by this object, false otherwise.
```

**3 .公共抽象布尔 equals(Object obj):** 检查两个 Permission 对象是否相等。

```java
Parameters:
obj - the object to be compared
Returns:
true if both Permission objects are equal, false otherwise.
```

**4.public 抽象 int hashCode():** 它返回这个 Permission 对象的哈希代码值。

```java
Returns:
a hash code value for this object.
```

**5 .公共最终字符串 getName():** 它返回此权限的名称。

```java
Returns:
the name of this Permission.
```

**6 .公共抽象字符串 getActions():** 它以字符串格式返回此权限对象的操作。

```java
Returns:
the actions of this Permission.
```

**7 . public PermissionCollection new PermissionCollection()**:返回一个新的 PermissionCollection 对象。

```java
Returns:
a new PermissionCollection object
```

**8 .公共字符串 toString():** 它返回指定权限对象的字符串表示形式。

```java
Returns:
string representation of the specified Permission object.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.lang.management.ManagementPermission;
import java.security.Permission;

public class GFG {

    public static void main(String[] args)
    {
        // Creating a new ManagementPermission object with
        // name control
        Permission p = new ManagementPermission("control");
        try {
            // Printing name of the object
            System.out.println("Name: " + p.getName());
            // Printing hash value of the object
            System.out.println("Hashcode: " + p.hashCode());
            // Printing actions of the object
            System.out.println("Actions: "
                               + p.getActions());
            // Converting this managementPermission object
            // to new PermissionCollection object
            System.out.println(
                "As a new PermissionCollection object: "
                + p.newPermissionCollection().toString());
            // Checking if new permissionCollection implies
            // managementPermission object or not
            System.out.println(
                "Implies: "
                + p.newPermissionCollection().implies(p));
        }
        catch (Exception e) {
            System.err.println(e.toString());
        }
    }
}
```

**Output**

```java
Name: control
Hashcode: 951543133
Actions: 
As a new PermissionCollection object: java.security.BasicPermissionCollection@5b6f7412 (
)

Implies: false

```