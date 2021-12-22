# java 中的 java.net.URLPermission 类

> 原文:[https://www . geesforgeks . org/Java-net-URL permission-class-in-Java/](https://www.geeksforgeeks.org/java-net-urlpermission-class-in-java/)

URLPermission 类用于表示访问给定 URL 的资源的权限。给定的*网址*作为许可的*名称*。*动作*代表请求方法和标题。

**类申报:**

```java
public final class URLPermission
extends Permission
```

**构造函数:**

<figure class="table">URLPermission(字符串 URL，T31)

| **constructor** | **Description** |
| --- | --- |
| urlPermission(字符串 URL)

 | 该构造函数用于用指定的 URL 创建 URLPermission 类的新实例 |

</figure>

**方法:**

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| 等于(Object p) | 此方法检查两个 URLPermission 对象是否相等。

 |
| 【getactivities() | 该方法以 String 格式返回动作，目前是一个规范化的方法列表，并发送请求头列表。 |
| hashCode() | 这个方法返回这个对象的哈希值。 |
| 隐含(Permission p) | 该方法检查给定的权限是否由该对象隐含。 |

</figure>

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate working of hashCode() method
import java.net.URLPermission;

public class URLpermission {

    public static void main(String[] args)
    {
        String url = "https://www.geeksforgeeks.org";
        // creating a new URLPermission object
        URLPermission permission
            = new URLPermission(url, "connect");
        // printing the actions of this URLPermission object
        System.out.println("Actions: "
                           + permission.getActions());
        // printing the hash value of this URLPermission
        // object
        System.out.println("Hashcode: "
                           + permission.hashCode());
    }
}
```

**Output**

```java
Actions: CONNECT:
Hashcode: -1592744539

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate working of equals() method
import java.net.URLPermission;

public class URLpermission {

    public static void main(String[] args)
    {
        String url1 = "https://www.geeksforgeeks.org";
        String url2
            = "https://www.geeksforgeeks.org/data-structure-gq/linked-list-gq/";
        URLPermission permission1 = new URLPermission(url1);
        URLPermission permission2 = new URLPermission(url2);

        if (permission1.equals(permission2)) {
            System.out.println("Both objects are equal");
        }
        else {
            System.out.println(
                "Both objects are not equal");
        }
    }
}
```

**Output**

```java
Both objects are not equal

```