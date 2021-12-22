# Java 中的泛型构造函数和接口

> 原文:[https://www . geesforgeks . org/generic-构造函数和接口-in-java/](https://www.geeksforgeeks.org/generic-constructors-and-interfaces-in-java/)

[泛型](https://www.geeksforgeeks.org/generics-in-java/)创建一个类、接口和方法，考虑所有作为参数动态给出的(引用)类型。这确保了类型安全。从实例变量开始，类名后面的尖括号“< >”中指定了泛型类参数。

[泛型构造函数](https://www.geeksforgeeks.org/constructor-getgenericparametertypes-method-in-java-with-examples/)与泛型方法相同。对于公共关键字之后和类名之前的泛型构造函数，必须放置类型参数。定义泛型构造函数后，可以用任何类型的参数调用构造函数。构造函数是初始化新创建的对象的代码块。它是没有返回类型的实例方法。构造函数的名称与类名相同。构造函数可以是泛型的，尽管它的类不是泛型的。

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Generic constructors

// Importing input output classes
import java.io.*;

// Class 1
// Generic class
class GenericConstructor {
    // Member variable of this class
    private double v;

    // Constructor of this class where
    // T is typename and t is object
    <T extends Number> GenericConstructor(T t)
    {
        // Converting input number type to double
        // using the doubleValue() method
        v = t.doubleValue();
    }

    // Method of this class
    void show()
    {
        // Print statement whenever method is called
        System.out.println("v: " + v);
    }
}

// Class 2 - Implementation class
// Main class
class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Display message
        System.out.println("Number to Double Conversion:");

        // Creating objects of type GenericConstructor i.e
        // og above class and providing custom inputs to
        // constructor as parameters
        GenericConstructor obj1
            = new GenericConstructor(10);
        GenericConstructor obj2
            = new GenericConstructor(136.8F);

        // Calling method - show() on the objects
        // using the dot operator
        obj1.show();
        obj2.show();
    }
}
```

**Output**

```
Number to Double Conversion:
v: 10.0
v: 136.8000030517578
```

输出说明:这里 *GenericConstructor()* 陈述了一个泛型类型的参数，它是 Number 的子类。*泛型构造函数()*可以用整数、浮点或双精度等任何数值类型调用。所以，尽管 *GenericConstructor()* 不是泛型类，它的构造函数是泛型的。

[Java 中的泛型接口](https://www.geeksforgeeks.org/bounded-types-generics-java/) 是处理抽象数据类型的接口。接口帮助从表示细节独立操作 java 集合。它们用于在 java 中实现多重继承，形成层次结构。它们不同于 java 类。这些只包括所有抽象方法，只有静态和最终变量。唯一可以创建的引用是接口[、](https://www.geeksforgeeks.org/generics-in-java/)而不是对象，不像类，这些不包含任何构造函数、实例变量。这涉及到“[实现](https://www.geeksforgeeks.org/extends-vs-implements-in-java/)关键字。这些类似于泛型类。

通用接口的优势如下:

1.  这是为不同的数据类型实现的。
2.  它允许对实现接口的数据类型设置约束，即界限。

**语法:**

```
interface interface-Name < type-parameter-list > {//....}

class class-name <type-parameter-list> implements interface-name <type-arguments-list> {//...}
```

**实现:**下面的例子创建了一个接口‘最小最大值’，它包含了一些非常基本的方法，比如最小()，最大值()，只是为了说明当它们返回给定对象的最小值和最大值时。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Generic interfaces

// Importing java input output classes
import java.io.*;

// An interface that extends Comparable
interface MinMax<T extends Comparable<T> > {
    // Declaring abstract methods
    // Method with no body is abstract method
    T min();
    T max();
}

// Class 1 - Sub-class
// class extending Comparable and implementing interface
class MyClass<T extends Comparable<T> >
    implements MinMax<T> {

    // Member variable of 'MyClass' class
    T[] values;

    // Constructor of 'MyClass' class
    MyClass(T[] obj) { values = obj; }

    // Now, defining min() and max() methods
    // for MimMax interface computation

    // Defining abstract min() method
    public T min()
    {
        // 'T' is typename and 'o1' is object_name
        T o1 = values[0];

        // Iterating via for loop over elements using
        // length() method to get access of minimum element
        for (int i = 1; i < values.length; i++)
            if (values[i].compareTo(o1) < 0)
                o1 = values[i];

        // Return the minimum element in an array
        return o1;
    }

    // Defining abstract max() method
    public T max()
    {
        // 'T' is typename and 'o1' is object_name
        T o1 = values[0];

        // Iterating via for loop over elements using
        // length() method to get access of minimum element
        for (int i = 1; i < values.length; i++)
            if (values[i].compareTo(o1) > 0)
                o1 = values[i];

        // Return the maximum element in an array
        return o1;
    }
}

// Class 2 - Main class
// Implementation class
class GFG {
    // Main driver method
    public static void main(String[] args)
    {
        // Custom entries in an array
        Integer arr[] = { 3, 6, 2, 8, 6 };

        // Create an object of type as that of above class
        // by declaring Integer type objects, and
        // passing above array to constructor
        MyClass<Integer> obj1 = new MyClass<Integer>(arr);

        // Calling min() and max() methods over object, and

        // printing the minimum value from array elements
        System.out.println("Minimum value: " + obj1.min());

        // printing the maximum value from array elements
        System.out.println("Maximum value: " + obj1.max());
    }
}
```

**Output**

```
Minimum value: 2
Maximum value: 8
```

输出说明:这里接口是用类型参数 T 声明的，它的上限是 Comparable，在 java.lang 中是这样的，这说明了如何根据对象的类型来比较对象。上面的 T 由 MyClass 声明，并进一步传递给 MinMax，因为 MinMax 需要一个实现 Comparable 的类型，实现类(MyClass)应该有相同的边界。

> **注意:**一旦建立了绑定，就不需要在 implements 子句中再次声明。如果一个类实现了泛型接口，那么这个类必须是泛型的，这样它就可以接受传递给接口的类型参数。