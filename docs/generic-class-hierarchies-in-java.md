# Java 中的泛型类层次结构

> 原文:[https://www . geesforgeks . org/generic-class-hierarchy-in-Java/](https://www.geeksforgeeks.org/generic-class-hierarchies-in-java/)

泛型是指 java5 中引入的参数化类型。这些有助于创建类、接口、方法等。在参数化类型上工作的类或方法，称为“泛型类”或“泛型方法”。泛型是泛型类型和方法的定义和使用的语言属性的组合。集合在泛型之前使用，泛型包含任何类型的对象，即非泛型。使用泛型，可以创建一个类、接口或方法来自动处理所有类型的数据(整数、字符串、浮点等)。它扩展了安全轻松地重用代码的能力。泛型还提供类型安全(确保在执行操作之前对正确类型的数据执行操作)。

继承允许分级分类。超类是一个继承的类。子类是一个继承的类。它继承了由超类定义的所有成员，并添加了自己独特的元素。这些使用[扩展](https://www.geeksforgeeks.org/extends-vs-implements-in-java/)作为关键词。

有时泛型类的行为类似于超类或子类。在泛型层次结构中，所有子类都向上移动任何参数类型，这些参数类型是层次结构中泛型的超类所必需的。这与构造函数参数在层次结构中上移是一样的。

**例 1:** 通用超类

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate generic class hierarchies

// Importing all input output classes
import java.io.*;

// Helper class 1
// Class 1 - Parent class
class Generic1<T> {
    // Member variable of parent class
    T obj;

    // Constructor of parent class
    Generic1(T o1) { obj = o1; }

    // Member function of parent class
    // that returns an object
    T getobj1() { return obj; }
}

// Helper class 2
// Class 2 - Child class
class Generic2<T, V> extends Generic1<T> {
    // Member variable of child class
    V obj2;
    Generic2(T o1, V o2)
    {
        // Calling super class using super keyword
        super(o1);

        obj2 = o2;
    }

    // Member function of child class
    // that returns an object
    V getobj2() { return obj2; }
}

// Class 3 -  Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating Generic2 (sub class) object
      // Custom inputs as parameters
        Generic2<String, Integer> x
            = new Generic2<String, Integer>("value : ",
                                            100);

        // Calling method and printing
        System.out.println(x.getobj1());
        System.out.println(x.getobj2());
    }
}
```

**Output**

```java
value : 
100
```

> **注意:**如果需要，子类可以自由添加自己的类型参数。

**例 2:** 非泛型子类的泛型子类

T5】JavaT7

```java
import java.io.*;
// non-generic super-class
class NonGen {
    int n;
    NonGen(int i) { n = i; }
    int getval() { return n; }
}
// generic class sub-class
class Gen<T> extends NonGen {
    T obj;
    Gen(T o1, int i)
    {
        super(i);
        obj = o1;
    }
    T getobj() { return obj; }
}

class GFG {
    public static void main(String[] args)
    {

        Gen<String> w = new Gen<String>("Hello", 2021);

        System.out.println(w.getobj() + " " + w.getval());
    }
}
```

T8T10**输出**T1