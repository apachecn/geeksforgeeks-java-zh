# Java 中 Character.isHighSurrogate()方法，带示例

> 原文:[https://www . geeksforgeeks . org/character-ishightsurrogate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-ishighsurrogate-method-in-java-with-examples/)

**java . lang . character . IshighSuperation()**是 Java 中的一个内置方法，它确定给定的字符值是否是 Unicode 高替代代码单元(也称为前导替代代码单元)。这些值本身并不表示字符，而是用于表示 UTF-16 编码中的补充字符。

**语法:**

```java
public static boolean isHighSurrogate(char ch)

```

**参数:**该函数接受一个指定待测值的强制参数 *ch* 。

**返回值:**函数返回一个布尔值。如果字符值在最小 _ 高 _ 代理和最大 _ 高 _ 代理之间(含这两个值)，返回的值为*真*，否则为*假*。

下面的程序举例说明了 Character.isHighSurrogate()方法:

**程序 1:**

```java
// Java program to illustrate the
// Character.isHighSurrogate() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '\u0a4f', c2 = '\ud8b4';

        // assign isHighSurrogate results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isHighSurrogate(c1);
        System.out.println("c1 is a Unicode"+
        "high-surrogate code unit ? " + bool1);

        boolean bool2 = Character.isHighSurrogate(c2);
        System.out.println("c2 is a Unicode"+ 
        "high-surrogate code unit ? " + bool2);
    }
}
```

**Output:**

```java
c1 is a Unicodehigh-surrogate code unit ? false
c2 is a Unicodehigh-surrogate code unit ? true

```

**程序 2:**

```java
// Java program to illustrate the
// Character.isHighSurrogate() method
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create 2 char primitives c1, c2
        char c1 = '\u0b9f', c2 = '\ud5d5';

        // assign isHighSurrogate results of
        // c1, c2 to boolean primitives bool1, bool2
        boolean bool1 = Character.isHighSurrogate(c1);
        System.out.println("c1 is a Unicode" + 
        "high-surrogate code unit ? " + bool1);

        boolean bool2 = Character.isHighSurrogate(c2);
        System.out.println("c2 is a Unicode" + 
        "high-surrogate code unit ? " + bool2);
    }
}
```

**Output:**

```java
c1 is a Unicodehigh-surrogate code unit ? false
c2 is a Unicodehigh-surrogate code unit ? false

```