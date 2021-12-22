# java 中的 java.nio.file.LinkPermission 类

> 原文:[https://www . geesforgeks . org/Java-nio-file-link permission-class-in-Java/](https://www.geeksforgeeks.org/java-nio-file-linkpermission-class-in-java/)

java.nio.file.LinkPermission 类处理链接创建操作的权限。这些类允许权限如下:

<figure class="table">

| 

权限名称

 | 

什么许可允许

 | 

授予此权限的风险

 |
| --- | --- | --- |
| 困难的 | 此权限允许将现有文件添加到目录中。此操作也称为创建硬链接。 | 攻击者可能有权访问所有文件，因为该权限允许链接到文件系统中的任何文件。 |
| 符号的 | 该权限允许创建文件指针。此操作也称为创建软/符号链接。 | 攻击者可能有权访问所有文件，因为该权限允许链接到文件系统中的任何文件。 |

</figure>

**类申报:**

```java
public final class LinkPermission
extends BasicPermission
```

**施工方:**

<figure class="table">

| 构造器 | 描述 |
| --- | --- |
| 链接权限(字符串名称) | 此构造函数用于创建具有指定名称的链接权限。 |
| 链接权限(字符串名称、字符串操作) | 此构造函数用于创建具有指定名称和操作的链接权限。 |

</figure>

**从 java.security.BasicPermission 类继承的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 等于(对象对象) | 此方法检查两个基本权限对象是否相等 |
| 函数() | 此方法以字符串格式返回操作 |
| hashCode() | 此方法返回此对象的哈希代码值 |
| 暗示(许可权限) | 此方法检查该对象是否暗示了给定的权限 |
| newPermissionCollection() | 此方法返回一个新的 PermissionCollection 对象 |

</figure>

**示例 1:** 创建新硬链接的 Java 程序权限

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create a new hard LinkPermission
import java.nio.file.LinkPermission;
import java.security.Permission;

// Driver class
public class GFG {
    // Main method
    public static void main(String[] args)
    {
        try {
            // Creating a new LinkPermisson object
            Permission permission
                = new LinkPermission("hard");

            // Printing name of the permission
            System.out.println(permission.getName());

            // Printing class of the permission object
            System.out.println(permission.getClass());

            // Printing hash value of the permission object
            System.out.println(permission.hashCode());
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
hard
class java.nio.file.LinkPermission
3195115
```

**示例 2:** 创建新符号链接的 Java 程序权限

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create a new symbolic LinkPermission
import java.nio.file.LinkPermission;
import java.security.Permission;

// Driver class
public class GFG {
    // Main method
    public static void main(String[] args)
    {
        try {

            // Creating a new LinkPermisson object
            Permission permission
                = new LinkPermission("symbolic");

            // Printing name of the permission
            System.out.println(permission.getName());

            // Printing class of the permission object
            System.out.println(permission.getClass());

            // Printing hash value of the permission object
            System.out.println(permission.hashCode());
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
symbolic
class java.nio.file.LinkPermission
1787985074
```

**示例 3:** 比较两个 LinkPermission 对象的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compare two LinkPermission objects
import java.nio.file.LinkPermission;
import java.security.Permission;

// Driver class
public class GFG {
    // Main method
    public static void main(String[] args)
    {
        try {

            Permission hardPermission
                = new LinkPermission("hard");
            Permission softPermission
                = new LinkPermission("symbolic");

            // Checking is both permissions are equal or not
            if (hardPermission.equals(softPermission)) {
                System.out.println(
                    "Both permission are equal");
            }
            else {
                System.out.println(
                    "Both permission are not equal");
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
Both permission are not equal
```