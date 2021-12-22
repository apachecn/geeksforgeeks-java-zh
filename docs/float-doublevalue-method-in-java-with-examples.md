# Java 中的 Float doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/float-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/float-doublevalue-method-in-java-with-examples/)

[Float](https://www.geeksforgeeks.org/java-lang-float-class-java/) 类的 **doubleValue()** 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为双精度返回。

**语法** :

```java
FloatObject.doubleValue()
```

**返回值:**返回该浮点对象的**倍**值。

下面的程序用 Java 说明了 *doubleValue()* 方法:

**程序 1:**

```java
// Java code to demonstrate
// Float doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        // Float value
        float a = 17.65f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // doubleValue of the Float Object
        double output = b.doubleValue();

        // prdoubleing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**输出:**

```java
Float value of 17.65 is : 17.649999618530273

```

**程序二:**

```java
// Java code to demonstrate
// Float doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        // Float value
        float a = 6.0f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // doubleValue of the Float Object
        double output = b.doubleValue();

        // prdoubleing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**输出:**

```java
Float value of 6.0 is : 6.0

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # double value()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#doubleValue())