# 如何在 Java 中不创建对象的情况下执行实例初始化块(IIB)？

> 原文:[https://www . geesforgeks . org/如何执行-实例-初始化-block-iib-无需创建-java 中的对象/](https://www.geeksforgeeks.org/how-to-execute-instance-initialization-block-iib-without-creating-object-in-java/)

在 Java 程序中，可以对方法、构造函数和初始化块执行操作。实例初始化块或 IIB 用于初始化实例变量。我们知道实例块是 java 中的无名方法，我们可以在其中定义逻辑，并且它们具有某些特性。实例块逻辑对所有对象都是通用的，并且在创建过程中，每个对象只执行一次。现在，让我们通过创建对象来查看实例块的正常执行。

### **演示 1:** 实例块的正常执行

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Executing instance block
// by creating object.

// Class 1
// Helper class
class GFG {

    {
        // Creation of an instance block
        System.out.println("Instance block called by creating objects");
    }
}

// Class 2
// Main class
class GFGJava {

    // main driver method
    public static void main(String[] args)
    {

        // Object of 1st kind
        GFG obj1 = new GFG();

        // Object of 2nd kind
        GFG obj2 = new GFG();

        // Object of 3rd kind
        GFG obj3 = new GFG();
    }
}
```

**输出:**

```
Instance block called by creating objects
Instance block called by creating objects
Instance block called by creating objects
```

**解释:**对于每个对象创建，实例块只执行一次。这里对 obj1、obj2 和 obj3 执行。

### **演示 2:** 在不创建对象的情况下执行实例块

在演示 1 中，我们看到了通过创建明显的对象来执行实例块，但是有一种误解，认为不创建不真实的对象就不能执行实例块。在下一个演示中，我们将看到如何在不创建对象的情况下执行实例块。

## 爪哇

T0T6】

**输出:**

```
C:\Users\Bikash\Desktop\GeeksforGeeks Java>javac GFG.java
C:\Users\Bikash\Desktop\GeeksforGeeks Java>java GFG
Instance block inside main method called without creating an object
Instance block called by creating objects
Instance block called by creating objects
Instance block called by creating objects
```

**说明:**也可以在不创建对象的情况下执行实例块。要在不创建对象的情况下执行实例块，我们需要在主方法中显式定义它。