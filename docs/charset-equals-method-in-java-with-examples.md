# Java 中的 Charset equals()方法，示例

> 原文:[https://www . geesforgeks . org/charset-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-equals-method-in-java-with-examples/)

equals()方法是 **java.nio.charset** 的内置方法，用于检查 charset 的一个给定对象是否等于 charset 的另一个给定对象。当且仅当两个字符集具有相同的规范名称时，它们被认为是相等的。字符集永远不等于任何其他类型的对象。

**语法**:

```java
public final boolean equals(Object other)
```

**参数**:该函数接受单个强制参数**其他**，指定与之比较的参考对象。

**返回值**:该函数返回一个布尔值。如果相等，则返回真，否则返回假。

下面是上述功能的实现:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {
        // First charset
        Charset first = Charset.forName("ISO-2022-CN");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        System.out.println(first.equals(second));
    }
}
```

**Output:** 

```java
false
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // First charset
        Charset first = Charset.forName("UTF-8");

        // Second charset
        Charset second = Charset.forName("UTF-8");

        System.out.println(first.equals(second));
    }
}
```

**Output:** 

```java
true
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # equals-Java . lang . object-T4】