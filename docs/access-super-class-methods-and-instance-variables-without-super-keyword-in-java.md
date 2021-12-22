# 访问 Java 中没有超级关键字的超类方法和实例变量

> 原文:[https://www . geesforgeks . org/access-super-class-methods-and-instance-variables-不带-super-keyword-in-java/](https://www.geeksforgeeks.org/access-super-class-methods-and-instance-variables-without-super-keyword-in-java/)

类描述对象的属性和属性。一个类包含的主要包括以下组件。

1.  [**【修饰符】**](https://www.geeksforgeeks.org/access-specifiers-for-classes-or-interfaces-in-java/):Java 中的关键字，对类及其成员和方法提供了一组限制。
2.  **Class 关键字**:类的初始化是通过类的保留字并跟随类的名称来完成的。
3.  **类名**:在 java 中创建变量时必须遵循如下规则的类名。

**超级类:**可以从中创建许多子类的父类。所有子类都有父类的所有属性。**T3】**

**继承**是面向对象语言的机制，通过这种机制，任何类(子类)都可以继承其他类父类的所有属性和行为。

```
Parent class: GFG
Child  class: GFGChild

```

**简单继承格式:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Access Super Class Methods and Instance
// Variables Without Super Keyword in Java

import java.io.*;

class GFG {
    // super class (parent class)
    // instance variables
    // class methods
}

class GFGChild extends GFG {
    // GFGChild child class of GFG class
    // instance variables of GFGChild class
    // as well as GFG class
    // class methods of GFGChild class as well as GFG class
}
```

**子类中有两种方法调用超类(父类)的实例变量和方法。**

**1。First Method:** super 关键字是 java 中的保留词之一。Super 引用父类的对象。(参考[T3 到](https://www.geeksforgeeks.org/super-keyword/)[这篇](https://www.geeksforgeeks.org/super-keyword/)文章)。

**用途:**

*   我们可以在 super 关键字的帮助下调用父类的重写方法。
*   super()用于执行父类的构造函数，应该在派生类构造函数的第一行中使用。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Access Super Class Methods and Instance
// Variables With Super Keyword in Java
import java.io.*;

// super class
class helloworld {

    // instance variable
    String name = "helloworld is the name";
    void print()
    {
        System.out.println("This is the helloworld class");
    }
}
// derived class
class GFG1 extends helloworld {

    // invoking the instance variable of parent class
    String name = super.name;
    void print()
    {
        // calling the overriden method
        super.print();
        System.out.println("This is the GFG1 class");

        // printing the name
        System.out.println(name);
    }
}
class GFG {
    public static void main(String[] args)
    {
        // instance of the derived class
        GFG1 ob = new GFG1();

        // calling the unoverriden method print
        ob.print();
    }
}
```

**Output**

```
This is the helloworld class
This is the GFG1 class
helloworld is the name

```

**2。第二种方法:**继承后不用关键字 super 关键字，父类的所有方法和实例变量都被子类继承。所以我们可以在儿童课堂上指导他们。

```
GFG class: parent class
Arraylist class: Derived class
```

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Access Super Class Methods and Instance
// Variables Without Super Keyword in Java
class Arraylist extends GFG {
    void hello()
    {
        System.out.println("This is the Main class");
    }
    public static void main(String args[])
    {
        // calling the constructor
        Arraylist ob = new Arraylist();
        // calling the inherited name method
        ob.name();
    }
}
class GFG {
    GFG()
    { // constructor of the parent  class
        System.out.println("This is the constructor");
    }

    void name() { System.out.println("Hello world"); }
}
```

**Output**

```
This is the constructor
Hello world
```