# Java 中抽象和封装的区别，并举例

> 原文:[https://www . geesforgeks . org/Java 中抽象和封装的区别-示例/](https://www.geeksforgeeks.org/difference-between-abstraction-and-encapsulation-in-java-with-examples/)

<u>**[Java 中的封装](https://www.geeksforgeeks.org/encapsulation-in-java/)**</u>

 <u>Encapsulation is defined as the wrapping up of data under a single unit. It is the mechanism that binds together code and the data it manipulates. Another way to think about encapsulation is, it is a protective shield that prevents the data from being accessed by the code outside this shield.

从技术上讲，在封装中，一个类的变量或数据对任何其他类都是隐藏的，只能通过声明它们的自己类的任何成员函数来访问。
和封装一样，一个类中的数据对其他类是隐藏的，所以也称为数据隐藏。
封装可以通过将类中的所有变量声明为私有，并在类中编写公共方法来设置和获取变量的值来实现。

```
// Java program to demonstrate encapsulation

public class Encapsulate {

    // private variables declared
    // these can only be accessed by
    // public methods of class
    private String geekName;
    private int geekRoll;
    private int geekAge;

    // get method for age to access
    // private variable geekAge
    public int getAge()
    {
        return geekAge;
    }

    // get method for name to access
    // private variable geekName
    public String getName()
    {
        return geekName;
    }

    // get method for roll to access
    // private variable geekRoll
    public int getRoll()
    {
        return geekRoll;
    }

    // set method for age to access
    // private variable geekage
    public void setAge(int newAge)
    {
        geekAge = newAge;
    }

    // set method for name to access
    // private variable geekName
    public void setName(String newName)
    {
        geekName = newName;
    }

    // set method for roll to access
    // private variable geekRoll
    public void setRoll(int newRoll)
    {
        geekRoll = newRoll;
    }
}

// Class to access variables
// of the class Encapsulate
class TestEncapsulation {
    public static void main(String[] args)
    {
        Encapsulate obj = new Encapsulate();

        // setting values of the variables
        obj.setName("Harsh");
        obj.setAge(19);
        obj.setRoll(51);

        // Displaying values of the variables
        System.out.println("Geek's name: " + obj.getName());
        System.out.println("Geek's age: " + obj.getAge());
        System.out.println("Geek's roll: " + obj.getRoll());

        // Direct access of geekRoll is not possible
        // due to encapsulation
        // System.out.println("Geek's roll: " + obj.geekName);
    }
}
```

**Output:**

```
Geek's name: Harsh
Geek's age: 19
Geek's roll: 51

```

<u>**[Java 中的抽象](https://www.geeksforgeeks.org/abstraction-in-java-2/)**</u>

<u>数据抽象是一种属性，通过它，只有基本的细节才会显示给用户。琐碎的或非基本的单元不会显示给用户。汽车被看作是一辆汽车，而不是它的单个部件。</u>

<u>数据抽象也可以定义为只识别对象所需特征而忽略无关细节的过程。对象的属性和行为使其区别于其他类似类型的对象，也有助于对对象进行分类/分组。</u>

```
// Java program to illustrate the concept of Abstraction

abstract class Shape {
    String color;

    // these are abstract methods
    abstract double area();
    public abstract String toString();

    // abstract class can have a constructor
    public Shape(String color)
    {
        System.out.println("Shape constructor called");
        this.color = color;
    }

    // this is a concrete method
    public String getColor()
    {
        return color;
    }
}
class Circle extends Shape {
    double radius;

    public Circle(String color, double radius)
    {

        // calling Shape constructor
        super(color);
        System.out.println("Circle constructor called");
        this.radius = radius;
    }

    @Override
    double area()
    {
        return Math.PI * Math.pow(radius, 2);
    }

    @Override
    public String toString()
    {
        return "Circle color is "
            + super.color
            + "and area is : "
            + area();
    }
}

class Rectangle extends Shape {

    double length;
    double width;

    public Rectangle(String color,
                     double length,
                     double width)
    {

        // calling Shape constructor
        super(color);
        System.out.println("Rectangle constructor called");
        this.length = length;
        this.width = width;
    }

    @Override
    double area()
    {
        return length * width;
    }

    @Override
    public String toString()
    {
        return "Rectangle color is "
            + super.color
            + "and area is : "
            + area();
    }
}

public class Test {
    public static void main(String[] args)
    {
        Shape s1 = new Circle("Red", 2.2);
        Shape s2 = new Rectangle("Yellow", 2, 4);

        System.out.println(s1.toString());
        System.out.println(s2.toString());
    }
}
```

<u>**Output:**

```
Shape constructor called
Circle constructor called
Shape constructor called
Rectangle constructor called
Circle color is Redand area is : 15.205308443374602
Rectangle color is Yellowand area is : 8.0

```</u> 

<u><u>**抽象和封装的区别:**</u></u>

| 抽象 | 包装 |
| --- | --- |
| 抽象是获取信息的过程或方法。 | 而封装是包含信息的过程或方法。 |
| 在抽象中，问题是在设计或接口级别解决的。 | 而在封装中，问题是在实现级别解决的。 |
| 抽象是隐藏不想要的信息的方法。 | 而封装是一种将数据隐藏在单个实体或单元中的方法，以及一种保护信息不受外部影响的方法。 |
| 我们可以使用抽象类和接口来实现抽象。 | 而封装可以通过使用访问修饰符来实现，即私有、受保护和公共。 |
| 在抽象中，使用抽象类和接口隐藏了实现的复杂性。 | 在封装过程中，使用获取器和设置器的方法隐藏数据。 |
| 帮助执行抽象的对象被封装。 | 而导致封装的对象不需要抽象。 |</u>