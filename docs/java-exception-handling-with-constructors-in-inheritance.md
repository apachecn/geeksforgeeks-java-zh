# Java——继承中构造函数的异常处理

> 原文:[https://www . geesforgeks . org/Java-带继承构造函数的异常处理/](https://www.geeksforgeeks.org/java-exception-handling-with-constructors-in-inheritance/)

Java 提供了一种处理异常的机制。要了解异常处理，可以参考 java 中的[异常](https://www.geeksforgeeks.org/exceptions-in-java/)。在本文中，我们讨论了当涉及到[继承](https://www.geeksforgeeks.org/inheritance-in-java/)时，[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)的异常处理。在 Java 中，如果父类的构造函数抛出任何选中的异常，那么子类构造函数可以抛出相同的异常或其父类。如果父类或子类构造函数引发任何未检查的异常，这是没有问题的。子类构造函数可以抛出任意[未检查异常](https://www.geeksforgeeks.org/checked-vs-unchecked-exceptions-in-java/) 而无需寻找父类构造函数。

**理解构造函数调用的行为**

每当引发某个异常的方法被另一个方法调用时，调用方法负责处理该异常(调用方法是包含实际调用的方法；被调用的方法就是被调用的方法)。对于构造函数，父类构造函数由子类构造函数调用。这意味着子类构造函数负责处理父类构造函数引发的异常。

现在，处理异常有两种方法，一种是捕获异常，另一种是抛出异常。但是在构造器的情况下，我们不能使用[试捕机制](https://www.geeksforgeeks.org/flow-control-in-try-catch-finally-in-java/)来处理。原因是我们将代码放入 try 块中，这样可以引发异常，然后捕获它。引发异常的原因是对父类构造函数的调用，如 super()。这意味着如果我们想使用 try-catch 处理异常，如下图所示。

插图 1

```java
Child() {

    // Try- catch block 
    try 
    {
        super();
    } 

    catch (FileNotFoundException exc) 
    {
      // Handling exception(code)
    }
}
```

实际上，这是不正确的，因为对 super 的调用必须是子类构造函数中的第一个语句(参见 java 中的[super】](https://www.geeksforgeeks.org/super-keyword/)，如下图所示:

插图 2

```java
Child() {
   super(); // either called explicitly or added by the compiler in case of default constructor
   try {
       // your code 
      }
      catch(FileNotFoundException exc) {
       // handling code;  
      }
  }
```

因此异常不能被捕获(因为它不在 try 块中)，并且我们不能使用 try-catch 机制来处理它。这就是为什么我们需要抛出异常。下面的代码将编译良好，如下所示:

```java
// parent class constructor throws FileNotFoundException 
Child() throws FileNotFoundException  {
  super(); // either called explicitly or added by the compiler in case of default constructor
  try {
      // your code
     }
     catch(FileNotFoundException exc) {
      // handling code;  
     }
 }
```

**不同的用例:**

1.  父类构造函数不会引发任何选中的异常
2.  父类构造函数引发选中的异常

现在让我们详细讨论每个案例，并通过干净的 java 程序来证明。

**情况 1:** 父类构造函数不会抛出任何选中的异常

如果父类构造函数没有抛出任何异常，那么子类可以抛出任何异常或者什么都不抛出。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Exception handling with
// Constructors in inheritance where Parent class
// constructor does not throw any checked exception

// Class 1
// Parent class
class Parent {

    // Constructor of Parent class
    // Not throwing any checked exception
    Parent()
    {

        // Print statement whenever parent class
        // constructor is called
        System.out.println("parent class constructor");
    }
}

// Class 2
// Child class
public class Child extends Parent {

    // Constructor of child class
    Child()
    {

        // Print statement whenever child class
        // constructor is called
        System.out.println("child class constructor");
    }

    // main driver method
    public static void main(String[] args)
    {

        // Creating object of child class inside main()
        Child child = new Child();
    }
}
```

**Output**

```java
parent class constructor
child class constructor
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Exception handling with
// Constructors in inheritance where Parent class
// constructor does not throw any checked exception

// Class 1
// Parent class
class Parent {

    // Constructor of parent class
    // Not throwing any checked exception
    Parent()
    {

        // Print statement when constructor of
        // parent class is called
        System.out.println("parent class constructor");
    }
}

// Class 2
// Child class
public class Child extends Parent {
    Child() throws Exception
    {

        // Print statement when constructor of
        // child class is called
        System.out.println(
            "child class constructor throwing Exception");
    }

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Creating object of child class
        Child child = new Child();
    }
}
```

**Output**

```java
parent class constructor
child class constructor throwing Exception
```

**情况 2:** 父类构造函数抛出一个选中的异常

如果父类构造函数引发选中的异常，那么子类构造函数可以引发相同的异常或其超类异常。此时，子类构造函数必须抛出异常。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Exception handling with
// Constructors in inheritance where Child class constructor
// Not throwing exception of same type or its parent classes

// Importing I/O classes
import java.io.*;

// Class 1
// Parent class
class Parent {

    // Constructor of parent class
    // Throwing checked exception
    Parent() throws FileNotFoundException
    {

        // Print statement when
        // parent class constructor is called
        System.out.println(
            "parent class constructor throwing exception");
    }
}

// Class 2
// Child class
class Child extends Parent {

    // Constructor of child class
    Child()
    {
        // Print statement when
        // child class constructor is called
        System.out.println("child class constructor");
    }

    // Main driver method
    public static void main(String[] args) throws Exception
    {
        // Creating object of child class inside main()
        Child child = new Child();
    }
}
```

**输出**

```java
error: unreported exception FileNotFoundException; must be caught or declared to be thrown
    Child() {
            ^
```

> 为了解决这个错误，我们需要声明要抛出的异常。这些异常可以属于同一类或父类。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Exception handling with Constructors
// in Inheritance where we Resolve the Error we Need to
// Declare the Exceptions to be Thrown

// Importing I/O classes
import java.io.*;

// Parent class
class Parent {

    // throwing checked exception
    Parent() throws FileNotFoundException {

        System.out.println("parent class constructor throwing checked exception");
    }
}

public class Child extends Parent {

    Child() throws FileNotFoundException {

        System.out.println("child class constructor throwing same exception");
    }

    public static void main(String[] args) throws Exception {

        Child child = new Child();
    }
}
```

**输出**

```java
parent class constructor throwing checked exception
child class constructor throwing same exception
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Exception handling with
// Constructors in Inheritance where we Resolve the Error we
// Need to Declare the Exceptions to be Thrown

// Importing I/O classes

// Importing package
package package1;
// Importing required I/O classes
import java.io.*;

// Class 1
// Parent class
class Parent {

    // throwing checked exception
    Parent() throws FileNotFoundException
    {
        System.out.println(
            "parent class constructor throwing checked exception");
    }
}

// Class 2
// Child class
public class Child extends Parent {

    // It can also throw same exception or its parent
    // classes exceptions
    Child() throws IOException
    {

        System.out.println(
            "child class constructor throwing super-class exception");
    }

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Creating object of child class
        // inside main() method
        Child child = new Child();
    }
}
```

**输出**

```java
parent class constructor throwing checked exception
child class constructor throwing super-class exception
```