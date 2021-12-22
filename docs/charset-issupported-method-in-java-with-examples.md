# Java 中的 Charset isSupported()方法，示例

> 原文:[https://www . geesforgeks . org/charset-issupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-issupported-method-in-java-with-examples/)

**isSupported()** 方法是 **java.nio.charset** 检查给定字符集是否受支持的内置方法。

**语法**:

```java
public final boolean isSupported()
```

**参数**:该函数接受单个强制参数**字符集名称**，该参数指定要检查的规范名称或别名。

**返回值**:该函数返回一个**布尔值**。如果支持，则返回 true，否则返回 false。

**错误和异常**:函数抛出两个异常，如下图:

*   *illegalcharsetname exception*:如果给定的字符集名称非法，则抛出
*   *IllegalArgumentException* :如果给定的字符集名称为空，则抛出

下面是上述功能的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;

public class GFG {

    public static void main(String[] args)
    {
        try {
            System.out.println("ISO-2022-CN"
                               + " is supported or not? :"
                               + Charset.isSupported("ISO-2022-CN"));
        }
        catch (Exception e) {
            System.out.println("Exception: "
                               + e);
        }
    }
}
```

**Output:** 

```java
ISO-2022-CN is supported or not? :true
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;

public class GFG {

    public static void main(String[] args)
    {
        try {
            System.out.println("ISO is "
                               + "supported or not? :"
                               + Charset.isSupported("ISO"));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:** 

```java
ISO is supported or not? :false
```

**程序 3:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;

public class GFG {

    public static void main(String[] args)
    {
        try {
            System.out.println("NULL is "
                               + "supported or not? :"
                               + Charset.isSupported(""));
        }
        catch (Exception e) {
            System.out.println("Exception: "
                               + e);
        }
    }
}
```

**Output:** 

```java
Exception is java.nio.charset.IllegalCharsetNameException:
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # isSupported-Java . lang . string-T4】