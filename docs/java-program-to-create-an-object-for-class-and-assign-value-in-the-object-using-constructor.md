# 使用构造函数为类创建对象并在对象中赋值的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-create-object-for-class-and-assign-value-in-object-use-constructor/](https://www.geeksforgeeks.org/java-program-to-create-an-object-for-class-and-assign-value-in-the-object-using-constructor/)

**Java** 是最流行的编程语言之一。这是一种**面向对象编程**语言，这意味着我们可以创建类、对象和更多。它还支持继承、多态、封装等等。它用于从移动应用程序到基于网络的应用程序的所有应用程序。**类被定义为蓝图**或模板，我们可以从中创建对象，对象是类的实例，由状态和行为组成。

**进场:**

*   首先，**定义一个名称为“SampleClass”的类**，**定义一个构造函数方法。**
*   **构造器**将始终具有与类名称相同的**名称，并且它不具有**返回**类型。**
*   构造函数用于实例化类的变量。
*   现在，使用构造函数，我们可以赋值。
*   在构造函数方法之后，实现一个返回任何变量的值的函数。
*   现在在主功能**中使用****【新建】关键字创建一个对象**。**如果该类没有**自定义构造函数**，则调用该类的**默认构造函数****否则**在创建对象时**根据与该类构造函数匹配的参数类型和数量调用自定义构造函数。****
*   **我们可以使用对象调用上面声明的函数。**
*   **最后使用 System.out.println()语句打印函数的值。**
*   **一旦你完成了实现，运行程序并得到输出。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to show the class declaration 
// and how to create an instance of this class

// Class Declaration 
public class Student
{
    // Instance Variables
    String name;
    String course;
    int age;

    // Constructor Declaration of Class
    public Student(String name, String course,int age)
    {
        this.name = name;
        this.course = course;
        this.age = age;
    }

    // method 1
    public String getName()
    {
        return name;
    }

    public static void main(String[] args)
    {
        // creating object using new operator
        Student s1 = new Student("Ravi","CSE",23);

        System.out.println(s1.getName());
    }
}
```

****输出:****

```
Ravi 
```

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to show the class declaration 
// and how to create an instance of this class

// Class Declaration 
public class Computer
{
    // Instance Variables
    String name;
    String config;
    int cost;
    String os;

    // Constructor Declaration of Class
    public Computer(String name, String config,
                   int cost, String os)
    {
        this.name = name;
        this.config = config;
        this.cost = cost;
        this.os = os;
    }

    // method 1
    public String getName()
    {
        return name;
    }

    // method 2
    public String getConfig()
    {
        return config;
    }

    // method 3
    public int getCost()
    {
        return cost;
    }

    // method 4
    public String getOs()
    {
        return os;
    }

    public static void main(String[] args)
    {
      // creating object using new operator
      Computer c1 = new Computer("Apple","i5", 50000, "IOS");

      System.out.println("The company name is "+ c1.getName());
      System.out.println("The configuration  is "+ c1.getConfig());
      System.out.println("Its Cost is "+ c1.getCost());
      System.out.println("Its operating System  "+ c1.getOs());

    }
}
```

****输出:****

```
The company name is Apple
The configuration  is i5
Its Cost is 50000
Its operating System  IOS 
```