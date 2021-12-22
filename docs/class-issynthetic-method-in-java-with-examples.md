# 类是 Java 中的综合()方法，带有示例

> 原文:[https://www . geeksforgeeks . org/class-isssynicious-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-issynthetic-method-in-java-with-examples/)

[**Java . lang . Class**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)的**issynamic()**方法用于检查该类是否为合成类。如果此类是合成类，则方法返回 true。否则返回 false。
**语法:**

```java
public boolean isSynthetic()
```

**参数:**此方法不接受任何参数。
**返回值:**如果这个类是合成类，这个方法返回**真**。否则返回**假**。
下面的程序演示了 isSynthetic()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate isSynthetic() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an synthetic
        // using isSynthetic() method
        System.out.println("Is Test an synthetic: "
                           + myClass.isSynthetic());
    }
}
```

**Output:** 

```java
Class represented by myClass: class Test
Is Test an synthetic: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate isSynthetic() method

// declaring an Annotation Type
@interface A {
    // interface element definitions
}

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for A
        Class myClass = A.class;

        // Check if myClass is an synthetic
        // using isSynthetic() method
        System.out.println("Is A an synthetic: "
                           + myClass.isSynthetic());
    }
}
```

**Output:** 

```java
Is A an synthetic: false
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # issynamic–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#isSynthetic--)