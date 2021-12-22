# Java 中不同的方法调用

> 原文:[https://www . geesforgeks . org/different-method-calls-in-Java/](https://www.geeksforgeeks.org/different-method-calls-in-java/)

Java 语言是所有编程语言中最流行的语言之一。使用 java 编程语言有几个优点，无论是出于安全目的还是构建大型分发项目。使用 Java 的一个优点是，Java 试图借助类等概念将语言中的每个概念与现实世界联系起来，JAVA 中的每个类都有自己的方法，要么是继承的方法，要么是用户定义的方法，用于定义类的行为。在本文中，我们将讨论不同类型的方法以及调用它们的方法。

**方法类型:**

1.  **用户自定义方法** s:这些是用户在特定类中实现的执行特定操作的方法。
2.  **抽象方法**:这些是不包含方法体，在抽象类内部实现的方法。
3.  **预定义方法**:这些是预定义的方法，可在 java 库中执行操作，例如 hashcode()方法。
4.  **静态方法**:这些方法无需类的任何实例即可访问。这些方法的内存管理不同于普通方法。

**方法类型 1:** 用户定义的方法

用户定义的非静态方法只能在类实例的帮助下调用或访问。

**语法:**

```
<ClassName> object=new <ClassName>
object.<MethodName>
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate User-Defined Methods

// Importing essential input output classes
import java.io.*;

// Class 1
class GFG {

    // Method 1
    // Method of this class
    void hello()
    {
        // Print statement whenever this method s called
        System.out.println("This is the userDefinedMethod");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Creating instance of the class
        // inside the main() method
        GFG ob = new GFG();

        // Calling the method of class 1
        // inside class 2
        ob.hello();
    }
}
```

**Output**

```
This is the userDefinedMethod
```

**方法类型 2:** 抽象方法

这些是在抽象类中声明的方法，没有实现特定签名的方法或者没有签名。我们不能称之为抽象方法。为了创建抽象类的实例，我们必须扩展抽象类。当我们必须以不同的方式使用方法的单向属性时，使用抽象方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Abstract Methods

// Class 1
// Helper class acting as Abstract class
abstract class GFGhelp {

    // Creating abstract method
    abstract void check(String name);
}

// Class 2
// Main class extending to helper class
public class GFG extends GFGhelp {

    // main driver method
    public static void main(String[] args)
    {
        // Creating the instance of the class
        GFG ob = new GFG();

        // Accessing the abstract method
        ob.check("GFG");
    }

    // Extends the abstract method
    @Override void check(String name)
    {
        System.out.println(name);
    }
}
```

**Output**

```
GFG
```

**方法类型 3:** 预定义方法

这些方法已经在 java 库中实现，或者是预定义的，并且被每个 java 类继承。例如，考虑 java 继承对象类中每个有不同方法的类。 [hashcode()](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) 是 Java 中每个类都继承的对象类的方法之一。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Predefined Methods

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of the class in
        // main() method
        GFG ob = new GFG();

        // Print the hashcode using
        // predefined hashCode() method
        System.out.println(ob.hashCode());
    }
}
```

**Output**

```
1023892928
```

**方法类型 4:** 静态方法

静态方法是那些不需要类实例访问的方法。基本上，这些方法是类方法，每个静态方法在所有实例之间平等共享。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Static Methods

// Importing input  output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // Static method
    static void hello()
    {

        // Print statement
        System.out.println("Hello");
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // calling the Method 1
        // Accessing method
        hello();
    }
}
```

```
Hello
```