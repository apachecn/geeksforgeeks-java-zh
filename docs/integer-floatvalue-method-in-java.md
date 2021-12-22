# Java 中的整数浮点值()方法

> 原文:[https://www . geesforgeks . org/integer-float value-method-in-Java/](https://www.geeksforgeeks.org/integer-floatvalue-method-in-java/)

java.lang 包的 Integer 类的 java.lang.Integer.floatValue()方法用于在扩展原语转换后将给定 Integer 的值转换为 float 类型。

**语法:**

```java
public float floatValue()
```

**参数:**该方法不接受任何参数。

**返回值:**方法将该对象转换为类型 float 后，返回该对象表示的数值。

下面的程序说明了 java.lang.Integer.floatValue()方法:
**程序 1:**

```java
// Java program to demonstrate working
// of java.lang.Integer.floatValue() method
import java.lang.Integer;

class Gfg {

    // Driver code
    public static void main(String args[])
    {
        Integer a = new Integer(28);

        // Convert Integer number to float value
        float b = a.floatValue();

        System.out.println(b);
    }
}
```

**Output:**

```java
28.0

```

**程序 2:**

```java
// Java program to demonstrate working
// of java.lang.Integer.floatValue() method
import java.lang.Integer;

class Gfg {
    // Driver code
    public static void main(String args[])
    {
        Integer a = new Integer(20);

        // Convert Integer number to float value
        float b = a.floatValue();

        System.out.println(b);
    }
}
```

**Output:**

```java
20.0

```