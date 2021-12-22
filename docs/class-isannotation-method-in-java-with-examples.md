# 类是 Java 中的符号()方法，带有示例

> 原文:[https://www . geesforgeks . org/class-is notation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-isannotation-method-in-java-with-examples/)

**是 [**java.lang.Class 类**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 的**方法，用于检查该类是否为注释类型。如果此类是批注类型，则方法返回 true。否则返回 false。
**语法:**

```
public boolean isAnnotation()
```

**参数:**此方法不接受任何参数。
**返回值:**如果该类为标注类型，则该方法返回**真**。否则返回**假**。
以下程序演示了 isAnnotation()方法。
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate isAnnotation() method

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Check if this class is an annotation
        // using isAnnotation() method
        System.out.println("Is Test an annotation: "
                           + myClass.isAnnotation());
    }
}
```

**Output:** 

```
Class represented by myClass: class Test
Is Test an annotation: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate isAnnotation() method

// declaring an Annotation Type
@interface A {
    // Annotation element definitions
}

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for A
        Class myClass = A.class;

        // Check if myClass is an annotation
        // using isAnnotation() method
        System.out.println("Is A an annotation: "
                           + myClass.isAnnotation());
    }
}
```

**Output:** 

```
Is A an annotation: true
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # is annotation–T4】