# Java 中的接口和多态性

> 原文:[https://www . geesforgeks . org/interfaces-and-多态-in-java/](https://www.geeksforgeeks.org/interfaces-and-polymorphism-in-java/)

Java 语言是所有编程语言中最流行的语言之一。使用 java 编程语言有几个优点，无论是出于安全目的还是构建大型分发项目。使用 JA 的优势之一是 Java 试图借助类、继承、多态、接口等概念将语言中的每个概念与现实世界联系起来。在本文中，我们将讨论多态性和接口概念。

多态性是指它有许多形式，这意味着一个特定的定义形式以许多不同的方式使用。最简单的现实例子是，假设我们必须存储这个人的姓名和电话号码，但是在很多情况下，一个人有两个不同的电话号码。我们必须用同一个名字保存同一个电话号码。

让我们帮忙解释一下。所以，在 java 中，这个问题可以用一个[面向对象的概念](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)、 *void insertPhone(String name，int phone)* 来解决。所以，这个方法用来保存特定人的电话号码。同样，我们可以使用相同的形式，但不同的签名意味着不同的参数来存储此人的替代电话号码 **void insertPhone(字符串名称，** **int phone1，** **int phone2)。** **一种方法有两种不同的形式，执行**不同的**操作。**这是多态性的一个例子，就是方法重载**。**

**Java 中多态性的类型**:

1.  运行时多态性
2.  编译时多态性

**类型 1:** [运行时间多态性](https://www.geeksforgeeks.org/difference-between-compile-time-and-run-time-polymorphism-in-java/)

这种类型的多态性由 java 虚拟机解决，而不是由 java 编译器解决。这就是为什么这种类型的多态性被称为运行时多态性。在 java 中，运行时多态性发生在方法重写期间。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Run-time polymorphism

// Importing I/O classes
import java.io.*;

// Class 1 (Parent class)
class GFG1 {
  //name method
  void name() {
    System.out.println("This is the GFG1 class");
  }
}

// Class 2 (Child class)
// Main class extending parent class
public class GFG extends GFG1 {

  // Method 1
  void name() {
    // Print statement
    System.out.println("This is the GFG class");
  }

  // Method 2
  // Main drive method
  public static void main(String[] args) {

    // Now creating 2 objects with different references and
    // calling the Method 1 over the objects

    // Case 1: GFG1 reference and GFG1 is the object
    GFG1 ob = new GFG1();
    ob.name();

    // Case 2: GFG1 reference and GFG is the object
    GFG1 ob1 = new GFG();
    ob1.name();
  }
}
```

**Output**

```
This is the GFG1 class
This is the GFG class
```

**输出解释:**

在上面的例子中，同一个函数，即名称被调用了两次，但是在这两种情况下，输出是不同的。这些方法的签名也是相同的。这就是为什么编译器不能识别哪个应该被执行。这只有在创建对象和引用类之后才能确定，这是在运行时(内存管理)执行的。这就是为什么这是运行时多态性。

**类型 2:** 编译时多态性

方法重载是编译时多态方法的一个例子。重载意味着一个函数具有相同的名称但不同的签名。这是编译时多态性，因为这种类型的多态性是在编译期间确定的，因为在编写代码期间，我们已经提到了同一函数名的不同类型的参数。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Run-time polymorphism

// Importing required classes
import java.io.*;
import java.util.*;

// Class 1
// Helper class
class First {

    // Method of this class
    // Without any parameter
    void check()
    {

        // Print statement if this method is called
        System.out.println("This is the class First");
    }
}

// Class 2
// Main class
class Second extends First {

    // Method overloading
    void check(String name)
    {
        // Printing the name of the class method having the
        // parameter
        System.out.println("This is the class " + name);
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Creating object of class 2
        Second ob = new Second();
        // Calling method over class 2 object
        ob.check("Second");

        // Creating object of class 1
        First ob1 = new First();
        ob.check();

        // Upcasting
        First ob2 = new Second();
        ob.check();
    }
}
```

**Output**

```
This is the class Second
This is the class First
This is the class First
```

[接口](https://www.geeksforgeeks.org/interfaces-in-java/)与类非常相似。它们有变量和方法，但是接口只允许抽象方法(不包含方法的主体)，但是类和接口之间有什么区别呢？第一个优点是允许接口在特定的类中实现多个继承。如果我们在类中扩展多个类，Java 语言不支持多个继承，但是在接口的帮助下，JAVA 中允许多个继承。

> **真实例子**
> 
> 接口的真实例子是，我们为在特定公司工作的不同级别的员工提供了多个类，该类的必要属性是员工的工资和这个。我们必须在每一个班级实施。而且，这里的每个员工都不一样。使用了接口的概念。我们只需创建一个包含抽象工资方法的接口，并在所有类中实现它，我们就可以轻松地定义员工的不同工资。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate Concept of interfaces

// Interface
interface salary {
    void insertsalary(int salary);
}

// Class 1
// Implementing the salary in the class
class SDE1 implements salary {
    int salary;
    @Override public void insertsalary(int salary)
    {
        this.salary = salary;
    }
    void printSalary() { System.out.println(this.salary); }
}

// Class 2
// Implementing the salary inside the SDE2 class
class SDE2 implements salary {
    int salary;
    @Override public void insertsalary(int salary)
    {
        this.salary = salary;
    }
    void printSalary() { System.out.println(this.salary); }
}

public class GFG {

    public static void main(String[] args)
    {
        SDE1 ob = new SDE1();
        // Insert different salaries
        ob.insertsalary(100000);
        ob.printSalary();
        SDE2 ob1 = new SDE2();

        ob1.insertsalary(200000);
        ob1.printSalary();
    }
}
```

**Output**

```
100000
200000
```