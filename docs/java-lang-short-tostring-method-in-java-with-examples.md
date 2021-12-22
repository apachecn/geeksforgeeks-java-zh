# Java 中的 Java.lang.Short toString()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-lang-short-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/java-lang-short-tostring-method-in-java-with-examples/)

### toString(短)

[java.lang.Short](https://www.geeksforgeeks.org/java-lang-short-class-java/) 的静态 **toString()** 方法返回一个表示指定短的新 String 对象。基数假定为 10。这是一个静态方法，因此调用这个方法不需要短类的对象。

**语法:**

```java
public static String toString(short b)

```

**参数:**该方法接受一个参数 **b** ，该参数是需要字符串表示的短值。

下面是 toString()方法在 Java 中的实现:

**例 1:**

```java
// Java program to demonstrate working
// of java.lang.Short.toString() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        short a = 515;

        // using toString()
        System.out.println("String value: "
                           + Short.toString(a));
    }
}
```

**Output:**

```java
String value: 515

```

**例 2:**

```java
// Java program to demonstrate working
// of java.lang.Short.toString() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        short a = 51;

        // using toString()
        System.out.println("String value: "
                           + Short.toString(a));
    }
}
```

**Output:**

```java
String value: 51

```

### toString()

[java.lang.Short](https://www.geeksforgeeks.org/java-lang-short-class-java/) 的非静态 **toString()** 方法返回一个代表这个 Short 对象值的 String 对象。该值被转换为带符号的十进制表示形式，并作为字符串返回，就像短值作为参数提供给 toString(short)方法一样。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受任何参数。

**返回:**这个方法返回这个 Short 对象的值的字符串表示形式，以 10 为基数。

下面是 toString()方法在 Java 中的实现:

**例 1:**

```java
// Java program to demonstrate working
// of java.lang.Short.toString() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {
        short a1 = 515;

        // create Short object
        Short a = new Short(a1);

        // using toString()
        System.out.println("String value: "
                           + a.toString());
    }
}
```

**Output:**

```java
String value: 515

```

**例 2:**

```java
// Java program to demonstrate working
// of java.lang.Short.toString() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {
        short a1 = 51;

        // create Short object
        Short a = new Short(a1);

        // using toString()
        System.out.println("String value: "
                           + a.toString());
    }
}
```

**Output:**

```java
String value: 51

```

**参考:**

*   [https://docs . Oracle . com/javase/9/docs/API/Java/lang/short . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/lang/Short.html#toString--)
*   [https://docs . Oracle . com/javase/9/docs/API/Java/lang/short . html # toString-short-](https://docs.oracle.com/javase/9/docs/api/java/lang/Short.html#toString-short-)