# Java 中的德米特里法则——最少知识原则

> 原文:[https://www . geesforgeks . org/Java 中的德米特里法则-最少知识原则/](https://www.geeksforgeeks.org/law-of-demeter-in-java-principle-of-least-knowledge/)

根据德米特里**定律，**类应该尽可能了解其他几个类并与之交互。它用于通过限制类与其他类的交互来放松耦合，以提供稳定性，因为更紧密的耦合会使程序难以维护。因此，当我们限制班级之间的交流时，我们可以执行最少知识的原则。局部对象在参数中传递，在方法中实例化，或者应该是实例变量。在德米特里法则中，一个方法不应该调用任何非本地对象的方法。

> 我们正试图阻止类似 A.getObjectB()的事情。getObjectC()。display()这种说法违反了德米特律法。

**方法:**德米特里法则

java 中最少知识的 4 个原则如下:

1.  对象 O 的方法 M 可以调用对象 O 本身的方法
2.  方法 M 可以调用任何参数 P 的方法
3.  方法 M 可以调用在 M 内创建的对象
4.  对象 O 中的方法 M 可以调用任何类型的对象的方法，这些对象是 O 的直接组件

**实施:**

现在让我们通过实现来了解它们，以便更好地理解

**方法 1:** 对象 O 的方法 M 可以调用 O 本身的方法。

封装在一个类中的方法可以调用封装在同一类中的其他方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Law of Demeter or
// Least knowledge principle
// where
// Method M of an object O can invoke
// the method of O itself

// Importing input output classes
import java.io.*;

// Class 1
// Helper class
class Helper {

    // Method of this class
    void M()
    {

        // Print statement whenever method is called
        System.out.println("hello from M()");

        // 'this' keyword is valid as method named-
        // anotherMethod() is encapsulated in the same class
        this.anotherMethod();
    }

    // Method of this class
    void anotherMethod()
    {

        // Print statement whenever method is called
        System.out.println(
            "I am anotherMethod() of same class");
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of above Helper class and
        // in the main() method
        Helper obj = new Helper();

        // Method M of an object O can invoke
        // the method of O itself
        obj.M();
    }
}
```

**Output**

```
hello from M()
I am anotherMethod() of same class
```

**方法 2:** 方法 M 可以调用任意参数 P 的方法

如果作为参数传递，方法 M 可以使用对象 P 的方法，因为对象 P 对于方法 M 是本地的

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Law of Demeter or
// Least knowledge principle
// where
// Method M can call methods of any parameter P

// Importing all input output classes
import java.io.*;

// Class 1
// Helper class 
class Human{

    // Method of Human class
    public void speak() {

        // Print message whenever function is called
        System.out.println("Hello Dog");
    }
}

// Class 2
// Helper class
class Dog{

    // Method of Dog class
    public void M(Human P) {

        // We can call methods of object
        // passed in our parameter
        P.speak();

        // Print message whenever function is called
        System.out.println("Bark(_-_)");
    }
}

// Class 3
// Main class
class Main {

    // Main driver method
    public static void main (String[] args) {

        // Creating object of Human Class and Dog class
        // inside the main method
        Human h = new Human();
        Dog obj = new Dog();

        // Method M calling any parameter P
      // M-> method of Dog class
      // h-> Human class object
        obj.M(h);
    }
}
```

**Output**

```
Hello Dog
Bark(_-_)
```

**方法 3:** 方法 M 可以调用 M 内创建的对象

如果方法 M 创建了一个对象，那么它可以使用该对象，因为该对象被认为是方法 M 的本地对象

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Law of Demeter or
// Least knowledge principle
// where
// Method M can call objects created within M

// Importing all input output classes
import java.io.*;

// Class 1
// Helper class 
class Human {

    // Method of thos class
    public void speak() {

        // Print statement whenever the method is called
        System.out.println("Hello Dog");
    }
}

// Class 2
// helper class
class Dog {

    // Method of Dog class
    public void M() {

        // We can use object P as it is local
        // to this method and satisfy 3rd law
        Human P = new Human();
        P.speak();

        // Print statement whenever the method is called
        System.out.println("Barks-_-");
    }
}

// Class 3
// Main class
class GFG {
    public static void main (String[] args) {

        // Creating an object of Dog class
        // in the main() method
        Dog obj = new Dog();

        // Method M can call objects created
        // within M
        obj.M();
    }
}
```

**方法 4:** 对象 O 中的方法 M 可以调用作为 O 的直接组件的任何类型的对象的方法

一个类的方法可以调用另一个类的方法，这些方法是它的[实例变量](https://www.geeksforgeeks.org/variables-in-java/)。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Law of Demeter or
// Least knowledge principle
// where
// Method M in object O can invoke methods
// of any type of object that is a direct component of O

// Importing all input output classes
import java.io.*;

// Class 1
// Helper class 
class Human {

    // Method of Human class
    public void speak() {

        // Print statement whenever the function is called
        System.out.println("Hello Dog!");
    }
}

// Class 2
// helper class
class Dog {

    // Instance Variable
    Human P;

    // Method of Dog class
    public void M() {

        // We can use P as it is an Instance Variable
        // of class dog
        P = new Human();

        // Calling speak() method over instance variable 
        P.speak();

        // Method of Dog class
        System.out.println("Barks!");
    }
}

// Main class
class Main {

    // Main driver method
    public static void main (String[] args) {

        // Creating object of Dog class
        // in the main() method 
        Dog obj = new Dog();

        obj.M();
    }
}
```

**Output**

```
Hello Dog!
Barks!
```