# Java 中抽象 vs 公共访问修饰符

> 原文:[https://www . geesforgeks . org/abstract-vs-public-access-modifier-in-Java/](https://www.geeksforgeeks.org/abstract-vs-public-access-modifier-in-java/)

Java 中的 Access Modifier 是用于定义类、变量和方法的范围的保留关键字。它还告诉我们子类创建是否可能，或者对象创建是否可能。

**抽象访问修饰符**是一个只适用于类和方法而不适用于变量的修饰符。如果我们将任何方法声明为抽象方法，那么该方法必须在相应类的子类中实现，因为抽象方法从不谈论实现。如果任何修饰符谈论实现，那么它与抽象修饰符形成非法组合。以类似的方式，如果对于任何 java 类，如果我们不被允许创建一个对象(因为部分实现)，那么这种类型的类我们必须用抽象修饰符来声明。

**例:**

## 爪哇

```
// Java program to illustrate Abstract Access Modifier

// Importing the required packages
import java.io.*;
import java.util.*;

// Class 1
// Helper abstract class
abstract class Vechile {

    // Declaring an abstarct method getNumberOfWheel
    abstract public int getNumberOfWheel();
}

// Class 2
// Helper class extending above abstract class
class Bus extends Vechile {

    // Giving the implementation
    // to the  parent abstarct method
    public int getNumberOfWheel() { return 7; }
}

// Class 3
// Helper class extending above abstract class
class Auto extends Vechile {

    // Giving the implementation
    // to the  parent abstarct method
    public int getNumberOfWheel() { return 3; }
}

// Class 4
// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating Bus object
        Bus b = new Bus();

        // Creating Auto object
        Auto a = new Auto();

        // Now getting and displaying
        // the number of wheels
        // for Bus by calling the
        // getNumberOfWheel method
        System.out.println("Number of wheels in bus is"
                           + " " + b.getNumberOfWheel());

        // Now getting and displaying
        // the number of wheels
        // for Auto by calling the
        // getNumberOfWheel method
        System.out.println("Number of wheels in Auto is"
                           + " " + a.getNumberOfWheel());
    }
}
```

**输出**

```
Number of wheels in bus is 7
Number of wheels in Auto is 3
```