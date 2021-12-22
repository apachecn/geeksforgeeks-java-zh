# Java 中的 Java.util.PropertyPermission 类

> 原文:[https://www . geesforgeks . org/Java-util-property permission-class-Java/](https://www.geeksforgeeks.org/java-util-propertypermission-class-java/)

此类用于属性权限。它扩展了**基本权限**。名称是属性的名称(“java.home”、“os.name”等)。命名约定遵循分层属性命名约定。此外，名称末尾可能会出现一个星号，跟在“.”后面，或其本身来表示通配符匹配。例如:“java。*”或“*”有效，“*java”或“a*b”无效。

在授予代码访问某些系统属性的权限之前，应该小心谨慎。例如，授予访问“java.home”系统属性的权限会给出有关系统环境(java 安装目录)的潜在恶意代码敏感信息。此外，授予访问“user.name”和“user.home”系统属性的权限会提供有关用户环境(用户的帐户名和主目录)的潜在恶意代码敏感信息。

**构造函数:**
**属性权限(字符串名称，字符串操作):**

*   使用指定的名称创建新的属性权限对象。
*   要授予的操作以包含一个或多个逗号分隔的关键字列表的字符串形式传递给构造函数。可能的关键词是“读”和“写”。它们的含义定义如下:
    **读:**读许可。允许调用 System.getProperty。
    **写:**写权限。允许调用 System.setProperty。

**方法:**

1.  **boolean equals(Object obj):** Checks two PropertyPermission objects for equality. Checks that obj is a PropertyPermission, and has the same name and actions as this object. It overrides **equals** in class **BasicPermission**.

    ```
    Syntax: public boolean equals(Object obj).
    Returns: true if obj is a PropertyPermission, and 
    has the same name and actions as this PropertyPermission object.
    Exception: NA.

    ```

    ```
    // Java code illustrating equals() method
    import java.util.*;
    class PropertyPermissionDemo
    {
        public static void main(String arg[])
        {
           // creating property permission
           PropertyPermission gfg = (new PropertyPermission("os.name", "read"));
           if(gfg.equals(new PropertyPermission("os.name", "read")))
               System.out.println("both have same name and action");
           else
               System.out.println("both have different name or action");
        }
    }
    ```

    输出:

    ```
    both have same name and action

    ```

2.  **String getActions():** Returns the “canonical string representation” of the actions. That is, this method always returns present actions in the following order: read, write. It overrides **getActions** in class **BasicPermission**.

    ```
    Syntax: public String getAction().
    Returns: the canonical string representation of the actions.
    Exception: NA.

    ```

    ```
    // Java code illustrating getAction() method
    import java.util.*;
    class PropertyPermissionDemo
    {
        public static void main(String arg[])
        {
           // creating property permission
           PropertyPermission gfg = (new PropertyPermission("os.name",
                       "read,write"));
           System.out.print(gfg.getName() + " has permission to " 
                    + gfg.getActions());
        }
    }
    ```

    输出:

    ```
    os.name has permission to read,write

    ```

3.  **int hashCode():** Returns the hash code value for this object. The hash code used is the hash code of this permissions name, that is, getName().hashCode(), where getName is from the Permission superclass. It overrides **hashCode** in **BasicPermission**.

    ```
    Syntax: public int hashCode().
    Returns: a hash code value for this object.
    Exception: NA.

    ```

    ```
    // Java code illustrating hashCode() method
    import java.util.*;
    class PropertyPermissionDemo
    {
        public static void main(String arg[])
        {
           // creating property permission
           PropertyPermission gfg = (new PropertyPermission("os.name",
                  "read,write"));
           System.out.print("hash code of the object is: " +
                  gfg.getName().hashCode());
        }
    }
    ```

    输出:

    ```
    hash code of the object is: -1228098475

    ```

4.  **boolean implies(Permission p):** This method checks if this PropertyPermission implies the specified Permission. This is done by checking p is PropertyPermission object, actions of p are subset of this object’s actions and if this object’s name implies p’s actions. It overrides **implies** in class **BasicPermission**.

    ```
    Syntax: public boolean implies(Permission p).
    Returns: true if obj is a PropertyPermission, and 
    has the same name and actions as this PropertyPermission object.
    Exception: NA.

    ```

    ```
    // Java code illustrating implies() method
    import java.util.*;
    class PropertyPermissionDemo
    {
        public static void main(String arg[])
        {
           // creating property permission
           PropertyPermission gfg = (new PropertyPermission("os.name",
                   "read,write"));
           if(gfg.implies(new PropertyPermission("os.name",
                   "read,write")))
               System.out.println(gfg.getName() + " has permission " 
                       + gfg.getActions());
        }
    }
    ```

    输出:

    ```
    os.name has permission read,write

    ```

5.  **PermissionCollection newPermissionCollection():** Returns a new PermissionCollection object for storing PropertyPermission objects.

    ```
    Syntax: public PermissionCollection newPermissionCollection().
    Returns: a new PermissionCollection object suitable 
    for storing PropertyPermissions.
    Exception: NA.

    ```

    ```
    // Java code illustrating newPermissionCollection() method
    import java.security.PermissionCollection;
    import java.util.*;
    class PropertyPermissionDemo
    {
        public static void main(String arg[])
        {
           // creating property permission
           PropertyPermission gfg = (new PropertyPermission("os.name",
                   "read"));
           // create property permissions collection
           PermissionCollection permission;
           permission = gfg.newPermissionCollection();
           permission.add(gfg);
           permission.add(new PropertyPermission("java.home.*",
                   "read,write"));

           if(permission.implies(gfg))
               System.out.println("java.home.*" + " has permission to "
                       + "read" );

        }
    }
    ```

    输出:

    ```
    java.home.* has permission to read

    ```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。