# java 中的 Java . lang . instrument . Class definition 类

> 原文:[https://www . geesforgeks . org/Java-lang-instrument-class definition-class-in-Java/](https://www.geeksforgeeks.org/java-lang-instrument-classdefinition-class-in-java/)

该类用于将提供的类和[类文件字节](https://www.geeksforgeeks.org/java-class-file/)绑定在一个类定义对象中。这些类提供了方法来提取关于类的类型和一个[对象](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-1-class-and-its-members/)的类文件字节的信息。这个类是 [java.lang.Object](https://www.geeksforgeeks.org/object-class-in-java/) 类的子类。

**类申报:**

```java
public final class ClassDefinition
extends Object
```

**建造师:**

<figure class="table">

| **Constructor** | **Description** |
| --- | --- |
| 类别定义(类别类,字节[]类文件) | This constructor creates a new instance of the class definition class by binding the provided class and class file bytes. |

</figure>

**方法:**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| getDefinitionClass() | 此方法用于获取此类的类类型 |
| getDefinitionClassFile() | 此方法用于获取包含新类文件的字节数组。 |

</figure>

**示例 1:** 创建新 ClassDefinition 对象的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create new ClassDefinition object
import java.lang.instrument.ClassDefinition;

// driver class
public class GFG {
    // demoClass
    static class demoClass {
        void msg() { System.out.println("GeeksForGeeks"); }
    }
    // main method
    public static void main(String[] args)
    {
        try {

            // creating demoClass object
            demoClass cls = new demoClass();

            // creating object of supplied class
            Class<?> theClass = cls.getClass();

            // creating array of class files
            byte[] classFiles = { 0 };

            // creating a new ClassDefinition object
            ClassDefinition classdefinition
                = new ClassDefinition(theClass, classFiles);
            System.out.println(
                "ClassDefinition object successfully created");
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
ClassDefinition object successfully created
```

**示例 2:** Java 程序说明 ClassDefinition 类方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate ClassDefinition class methods
import java.lang.instrument.ClassDefinition;

// driver class
public class GFG {

    // demoClass
    static class demoClass {
        void msg() { System.out.println("GeeksForGeeks"); }
    }

    // main method
    public static void main(String[] args)
    {
        try {

            // creating demoClass object
            demoClass cls = new demoClass();

            // creating object of supplied class
            Class<?> theClass = cls.getClass();

            // creating array of class files
            byte[] classFiles = { 0 };

            // creating a new ClassDefinition object
            ClassDefinition classdefinition
                = new ClassDefinition(theClass, classFiles);

            // printing the class
            System.out.println(
                classdefinition.getDefinitionClass());

            // printing array of bytes that contain class
            // files
            System.out.println(
                classdefinition.getDefinitionClassFile());
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**Output**

```java
class GFG$demoClass
[B@448139f0
```