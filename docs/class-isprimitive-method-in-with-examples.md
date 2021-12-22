# 类是示例中的 Primitive()方法

> 原文:[https://www . geesforgeks . org/class-is primitive-in-method-in-examples/](https://www.geeksforgeeks.org/class-isprimitive-method-in-with-examples/)

[**Java . lang . Class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的**是 Primitive()** 方法，用来检查这个类是否是 Primitive 类。如果此类是基元类，则方法返回 true。否则返回 false。
**语法:**

```
public boolean isPrimitive()
```

**参数:**此方法不接受任何参数。
**返回值:**如果这个类是原始类，这个方法返回**真**。否则返回**假**。
下面的程序演示了 isPrimitive()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate isPrimitive() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an primitive
        // using isPrimitive() method
        System.out.println("Is Test a primitive: "
                           + myClass.isPrimitive());
    }
}
```

**Output:** 

```
Class represented by myClass: class Test
Is Test a primitive: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate isPrimitive() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = int.class;

        // Check if myClass is an primitive
        // using isPrimitive() method
        System.out.println("Is myClass a primitive: "
                           + myClass.isPrimitive());
    }
}
```

**Output:** 

```
Is myClass a primitive: true
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # is primitive–T4】