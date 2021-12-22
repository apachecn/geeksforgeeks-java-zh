# Java 中 super 和 super()的区别举例

> 原文:[https://www . geesforgeks . org/super 和 super-in-Java-with-examples/](https://www.geeksforgeeks.org/difference-between-super-and-super-in-java-with-examples/)

在 java 中,“super”一词被预先定义为与父类相关。如果我们需要在一次操作中简化和调整标题，那么 java 中的 super 关键字指的是处理父类对象，而 super()处理父类构造函数。我们将首先讨论超级关键词的概念，然后讨论 super()的概念。

**概念:**超级关键词

java 中的 [super 关键字](https://www.geeksforgeeks.org/super-keyword/)是一个引用变量，用于引用父类对象。关键词“超级”带着继承的概念进入画面。基本上这种形式的 ***超*** 是用来在超类中没有构造函数存在的时候初始化超类变量的。另一方面，它通常用于访问超类的特定变量。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate super keyword

// Class 1
// Base class
// Here it is vehicle class
class Vehicle {

    // Attribute
    int maxSpeed = 120;
}

// Class 2
// sub class Car extending vehicle
class Car extends Vehicle {
    int maxSpeed = 180;

    // Method
    void display()
    {
        // Printing maxSpeed of parent class (vehicle) as
        // super keyword refers to parent class
        System.out.println("Maximum Speed: "
                           + super.maxSpeed);
    }
}

// Class 3
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of child class
        Car small = new Car();

        // Calling out method defined inside child class
        small.display();
    }
}
```

**Output**

```java
Maximum Speed: 120
```

现在我们已经看到，super 关键字指的是父类，可以从输出本身感知到。现在让我们详细讨论第二个被称为 super()的概念，更多的程序员对此知之甚少，并且几乎不了解它的全部

**概念:**超级()

super 关键字也可以用来访问父类构造函数，方法是在其后添加“()”，即 super()。另外请记住，根据具体情况，“super()”既可以调用参数构造函数，也可以调用非参数构造函数。

**示例:**

## Java

```java
// Java code to demonstrate super()

// Class 1
// Helper class
// Parent class - Superclass
class Person {

    // Constructor of superclass
    Person()
    {
        // Print statement of this class
        System.out.println("Person class Constructor");
    }
}

// Class 2
// Helper class
// Subclass extending the above  superclass
class Student extends Person {
    Student()
    {
        // Invoking the parent class constructor
        // with the usage of super() word
        super();

        // Print styatement whenever subclass constructor is
        // called
        System.out.println("Student class Constructor");
    }
}

// Class 3
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of subclass
        // inside main() method
        Student s = new Student();
    }
}
```

**输出:**

```java
Person class Constructor
Student class Constructor
```

最后，在充分理解以上主题后，让我们最终总结出它们之间的差异，这些差异以表格形式列出如下:

<figure class="table">

| 极好的 | super() |
| --- | --- |
| Java 中的 super 关键字是一个引用变量，用来引用父类对象。 | Java 中的 super()是一个引用变量，用来引用父类构造函数。 |
| 超级可以用来调用父类的‘变量和方法’。 | super()只能用来调用父类的构造函数。 |
| 要通过 super 关键字调用的变量和方法可以随时完成， | 调用 super()必须是派生类(Student)类构造函数中的第一条语句。 |
| 如果没有使用 super 关键字显式调用超类变量或方法，那么什么也不会发生 | 如果构造函数没有使用 super()显式调用超类构造函数，那么 Java 编译器会自动插入对超类的无参数构造函数的调用。 |

</figure>