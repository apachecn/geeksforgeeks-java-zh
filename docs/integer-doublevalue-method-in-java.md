# Java 中的整数双数值()方法

> 原文:[https://www . geesforgeks . org/integer-double value-in-method-Java/](https://www.geeksforgeeks.org/integer-doublevalue-method-in-java/)

java.lang 包的 Integer 类的 **doubleValue()** 方法用于在一个扩展的原语转换后，将给定整数的值转换为 Double 类型并返回。

**语法:**

```java
public double doubleValue()
```

**参数:**该方法不取任何参数。

**返回值:**该方法在转换为双精度类型后返回一个由该对象表示的数值。

下面的程序说明了 java.lang.Integer.doubleValue()方法。
**节目一:**

```java
// Code to illustrate doubleValue() method
import java.lang.Integer;

class Gfg {

// Driver code
    public static void main(String args[])
    {
        Integer a = new Integer(14);

        // Convert Integer number to double value
        double b = a.doubleValue();

        System.out.println(b);
    }
}
```

**Output:**

```java
14.0

```

**程序 2:**

```java
// Code to illustrate doubleValue() method
import java.lang.Integer;

class Gfg {

// Driver code
    public static void main(String args[])
    {
        Integer a = new Integer(120);

        // Convert Integer number to double value
        double b = a.doubleValue();

        System.out.println(b);
    }
}
```

**Output:**

```java
120.0

```