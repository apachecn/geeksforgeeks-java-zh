# 检查给定类是否是内部类的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查给定类是否是内部类/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-an-inner-class/)

[内部类](https://www.geeksforgeeks.org/inner-class-java/)是另一个类的成员，这个类基本上是非静态嵌套类，也就是说，如果一个类在另一个类里面，并且不是静态的，那么这个类被调用就称为内部类。

**内部类的类型** :

1.  [Nested inner class](https://www.geeksforgeeks.org/nested-classes-java/)
2.  Method [Local internal class](https://www.geeksforgeeks.org/local-inner-class-java/)
3.  [Anonymous inner class](https://www.geeksforgeeks.org/anonymous-inner-class-java/)
4.  [Static nested class](https://www.geeksforgeeks.org/nested-classes-java/)

**方法 1:**

1.  First, check whether the given class is a nested class.
2.  Further check whether the class is non-static or not.
    *   If both conditions are true, then the given class is an inner class.
3.  Now, in order to check whether the given class is a nested class, we use the [java.lang.class # getEnclosingclass ()](https://www.geeksforgeeks.org/class-getenclosingclass-method-in-java-with-examples/) method, which returns an instance of [class](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) , which represents the directly closed class of the object.
    *   If the class is a top-level class, then this method will return null.
    *   This means that the method returns null if the class is not nested.
4.  Further use the [method to check whether the given class is static.](https://www.geeksforgeeks.org/modifier-isstaticmod-method-in-java-with-examples/)

程序到 ***检查嵌套的内部类***

## Java

```java
// Java Program to Check if a Given Class is  an Inner Class

// Importing package where Modifier is defined
import java.lang.reflect.Modifier;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating as GFG class object
        GFG gfg = new GFG();

        // Creating a InnerClass object
        InnerClass innerClass = gfg.new InnerClass();

        // Creating a Static Nested Class object
        StaticNestedClass statNested
            = new StaticNestedClass();

        // getClass() method of an object returns a
        // java.lang.Class instance representing the class
        // of the object
        Class classInstance1 = innerClass.getClass();
        Class classInstance2 = statNested.getClass();

        // Checking if the given classes are nested

        // getEnclosinglClass() of Class instance returns a
        // class object representing the immediate enclosing
        // class of the instance

        boolean isNested1
            = classInstance1.getEnclosingClass() != null;
        // classInstance1() method returns a Class object

        // If the specified class is a top-level class, then
        // it would returns null

        boolean isNested2
            = classInstance2.getEnclosingClass() != null;

        //  Check if the given classes are static

        // getModifiers() method of a class returns the
        // modifiers of the class encoded as an integer

        // Modifiers.isStatic returns true if the class
        // has a static modifier elsereturns false
        boolean isStatic1 = Modifier.isStatic(
            classInstance1.getModifiers());
        boolean isStatic2 = Modifier.isStatic(
            classInstance2.getModifiers());

        // If the given classes are nested and non-static,
        // then given classes are surely inner classes

        // Display message
        System.out.println(
            "Is innerClass an inner class object? : "
            + (isNested1 && !isStatic1));

        // Display message
        System.out.println(
            "Is statNested an inner class object? : "
            + (isNested2 && !isStatic2));
    }

    // Inner Class
    class InnerClass {
    }

    // Static nested class
    static class StaticNestedClass {
    }
}
```

**输出**

```java
Is innerClass an inner class object? : true
Is statNested an inner class object? : false
```