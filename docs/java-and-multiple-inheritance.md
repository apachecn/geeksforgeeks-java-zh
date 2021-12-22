# Java 和多重继承

> 原文:[https://www . geesforgeks . org/Java 和多重继承/](https://www.geeksforgeeks.org/java-and-multiple-inheritance/)

多重继承是面向对象概念的一个特征，其中一个类可以继承多个父类的属性。当超类和子类中存在具有相同签名的方法时，就会出现这个问题。在调用方法时，编译器无法确定要调用哪个类方法，甚至在调用哪个类方法时也无法确定优先级。

> **注意:** Java 不支持多重继承

**例 1:**

## 爪哇

```java
// Java Program to Illustrate Unsupportance of
// Multiple Inheritance

// Importing input output classes
import java.io.*;

//  Class 1
// First Parent class
class Parent1 {

  // Method inside first parent class
  void fun() {

    // Print statement if this method is called
    System.out.println("Parent1");
  }
}

// Class 2
// Second Parent Class
class Parent2 {

  // Method inside first parent class
  void fun() {

    // Print statement if this method is called
    System.out.println("Parent2");
  }
}

// Class 3
// Trying to be child of both the classes
class Test extends Parent1, Parent2 {

  // Main driver method
  public static void main(String args[]) {

    // Creating object of class in main() method
    Test t = new Test();

    // Trying to call above functions of class where
    // Error is thrown as this class is inheriting
    // multiple classes
    t.fun();
  }
}
```