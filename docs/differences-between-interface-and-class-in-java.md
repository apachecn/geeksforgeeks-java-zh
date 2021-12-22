# Java 中接口和类的区别

> 原文:[https://www . geesforgeks . org/Java 中接口和类之间的差异/](https://www.geeksforgeeks.org/differences-between-interface-and-class-in-java/)

本文重点介绍了 Java 中的一个[类](https://www.geeksforgeeks.org/classes-objects-java/)和一个[接口](https://www.geeksforgeeks.org/interfaces-in-java/)之间的区别。它们在语法上看起来很相似，都包含方法和变量，但它们在许多方面是不同的。
[**<u>类</u>**](https://www.geeksforgeeks.org/classes-objects-java/)**<u>:</u>**
类是用户定义的蓝图或原型，从中创建对象。它表示一种类型的所有对象共有的一组属性或方法。一般来说，类声明可以包括这些组件，顺序为:

1.  **修饰符**:类可以是公共的，也可以是默认访问的(详见[本](https://www.geeksforgeeks.org/access-specifiers-for-classes-or-interfaces-in-java/))。
2.  **类名:**名称应以首字母(按惯例大写)开头。
3.  **超类(如果有的话):**类的父类(超类)的名称，如果有的话，前面加关键字 extends。一个类只能扩展(子类)一个父类。
4.  **接口(如果有):**类实现的以逗号分隔的接口列表(如果有)，前面有关键字 implements。一个类可以实现多个接口。
5.  **Body:** 大括号包围的类体，{ }。

构造函数用于初始化新对象。字段是提供类及其对象状态的变量，方法用于实现类及其对象的行为。
**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate Class

// Class Declaration
public class Dog {

    // Instance Variables
    String name;
    String breed;
    int age;
    String color;

    // Constructor Declaration of Class
    public Dog(String name, String breed,
               int age, String color)
    {
        this.name = name;
        this.breed = breed;
        this.age = age;
        this.color = color;
    }

    // method 1
    public String getName()
    {
        return name;
    }

    // method 2
    public String getBreed()
    {
        return breed;
    }

    // method 3
    public int getAge()
    {
        return age;
    }

    // method 4
    public String getColor()
    {
        return color;
    }

    @Override
    public String toString()
    {
        return ("Hi my name is "
                + this.getName()
                + ".\nMy breed, age and color are "
                + this.getBreed() + ", "
                + this.getAge() + ", "
                + this.getColor());
    }

    public static void main(String[] args)
    {
        Dog tuffy = new Dog("tuffy", "papillon",
                            5, "white");
        System.out.println(tuffy.toString());
    }
}
```

**Output:** 

```java
Hi my name is tuffy.
My breed, age and color are papillon, 5, white
```

[**<u>接口</u>**](https://www.geeksforgeeks.org/interfaces-in-java/)**<u>:</u>**
像类一样，一个接口可以有方法和变量，但是接口中声明的方法默认是抽象的(只有方法签名，没有主体)。

*   接口指定类必须做什么，而不是如何做。它是班级的蓝图。
*   接口是关于功能的，比如玩家可以是一个接口，任何实现玩家的类都必须能够(或者必须实现)移动()。所以它指定了类必须实现的一组方法。
*   如果一个类实现了一个接口，并且没有为接口中指定的所有函数提供方法体，那么这个类必须被声明为抽象的。
*   一个 Java 库的例子是，[比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)。如果一个类实现了这个接口，那么它可以用来对集合进行排序。

**语法:**

```java
interface <interface_name> {

    // declare constant fields
    // declare methods that abstract 
    // by default.
}
```

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// working of interface.

import java.io.*;

// A simple interface
interface in1 {

    // public, static and final
    final int a = 10;

    // public and abstract
    void display();
}

// A class that implements the interface.
class testClass implements in1 {

    // Implementing the capabilities of
    // interface.
    public void display()
    {
        System.out.println("Geek");
    }

    // Driver Code
    public static void main(String[] args)
    {
        testClass t = new testClass();
        t.display();
        System.out.println(a);
    }
}
```

**Output:** 

```java
Geek
10
```

**<u>类和接口的区别:</u>**

<figure class="table">

| 班级 | 连接 |
| --- | --- |
| 用于创建类的关键字是“类” | 用于创建接口的关键字是“interface” |
| 一个类可以被实例化，即一个类的对象可以被创建。 | 不能实例化接口，即不能创建对象。 |
| 类不支持多重继承。 | 接口支持多重继承。 |
| 它可以继承另一个类。 | 它不能继承类。 |
| 它可以由另一个使用关键字“extends”的类继承。 | 它可以通过使用关键字“implements”由类继承，也可以通过使用关键字“extends”由接口继承。 |
| 它可以包含构造函数。 | 它不能包含构造函数。 |
| 它不能包含抽象方法。 | 它只包含抽象方法。 |
| 类中的变量和方法可以使用任何访问说明符(公共、私有、默认、受保护)来声明 | 接口中的所有变量和方法都声明为公共的。 |
| 类中的变量可以是静态的、最终的或者两者都不是。 | 所有变量都是静态的和最终的。 |

</figure>