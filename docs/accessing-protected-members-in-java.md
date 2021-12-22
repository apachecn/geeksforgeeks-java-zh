# 访问 Java 中的受保护成员

> 原文:[https://www . geesforgeks . org/access-protected-members-in-Java/](https://www.geeksforgeeks.org/accessing-protected-members-in-java/)

在 Java 中，有四种类型的访问修饰符。它们是公共的、私有的、默认的和受保护的。要了解这些修饰符的概念，可以参考 java 中的[访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)。在本文中，我们讨论了不同情况下受保护成员的可访问性。

现在让我们讨论访问受保护成员的各种场景，如下所示:

1.  在同一个类中访问
2.  在同一包的其他类中访问
3.  在同一个包中访问子类中受保护的类成员
4.  访问不同包中的另一个类
5.  在不同包的子类中访问

**情况 1:** 访问同一类中的受保护成员

> 我们可以在任何地方访问类的受保护成员。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate
// Accessing Protected Members
// in the same class

// Main class 
class Sample {

    protected int year = 2021;
    protected void printYear()
    {
        System.out.println("Its " + year + " !!");
    }

    public static void main(String[] args)
    {
        Sample sample = new Sample();
        System.out.println(sample.year);
        sample.printYear();
    }
}
```

**Output**

```
2021
Its 2021 !!
```

**情况 2:** 访问同一包的其他类中的受保护成员

> 我们可以访问同一个包中存在的另一个类的受保护成员。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Accessing
// Protected Members
// In Other Class of Same Package

// Class 1
class Sample {
    protected int year = 2021;
    protected void printYear() {
        System.out.println("Its "+year+" !!");
    }
}

// Class 2
public class Test {

    // Main driver method
    public static void main(String[] args) {
        Sample sample = new Sample();
        System.out.println(sample.year);
        sample.printYear();
    }
}
```

**Output**

```
2021
Its 2021 !!
```

**情况 3:** 访问同一个包中子类中某个类的受保护成员

> 如果一个类的子类中的受保护成员都存在于同一个包中，我们就可以访问它们。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate
// Accessing Protected Members
// of a class in its subclass
// in the same package

// Class 1
class Sample {
    static protected String title = "geekforgeeks";
    protected int year = 2021;
    protected void printYear() {
        System.out.println("Its "+year+" !!");
    }
}

// Class 2
public class Test extends Sample {
    public static void main(String[] args) {
        Sample sample = new Sample();
        System.out.println(sample.year);
        sample.printYear();
        System.out.println(Sample.title);
    }
}
```

**Output**

```
2021
Its 2021 !!
geekforgeeks
```

**情况 4:** 访问不同包中另一个类的受保护成员

> 我们不能访问存在于不同包中的类(非子类)中的受保护成员。

**例 1:** 包装 1

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate
// Accessing Protected Members
// In Another Class in a
// Different Package

// Package 1
package package1;

// Main class
public class Sample {

    static protected String title = "geeksforgeeks";
    protected int year = 2021;

    // Protected method
    protected void printYear() {
        System.out.println("Its "+year+" !!");
    }
}
```

**例 2:** 包 2

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate
// Accessing Protected Members
// In Another Class in a
// Different Package

// Package 1
package package2;
// Importing above package
import package1.Sample;

// Main class
public class Test {

    // Main driver method
    public static void main(String[] args) {

        Sample sample = new Sample();
        System.out.println(sample.year);
        sample.printYear();
        System.out.println(Sample.title);
    }
}
```

**输出:**

```
error: year has protected access in Sample
                System.out.println(sample.year);
                                         ^
error: printYear() has protected access in Sample
                sample.printYear();
                      ^
error: title has protected access in Sample
                System.out.println(Sample.title);
                                           ^
```

它会给出编译时错误。在下面的例子中，我们将创建两个类。包 1 中的示例类和包 2 中的测试类，并尝试访问测试类中示例类的受保护成员。上面两个例子证明了这一点。

**情况 5:** 访问不同包中子类中的受保护成员

我们可以访问存在于不同包中的子类的受保护成员。在下面的例子中，我们将创建两个类。包 1 中的示例类和包 2 中的子类。子类扩展了示例类。

**例 1.1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Accessing Protected
// Members in sub-class in a different package

package package1;

// Class
public class Sample {

    // Protected attributes
    static protected String title = "geeksforgeeks";
    protected int year = 2021;
    protected void printYear()
    {
        System.out.println("Its " + year + " !!");
    }
}
```

**例 1.2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Accessing Protected
// Members in Sub-class in a different Package
package package2;
// Importing class from above package
import package1.Sample;

// Main class
public class Child extends Sample {

    // Method 1
    void helper()
    {
        System.out.println(year);
        printYear();
        System.out.println(Sample.title);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating child class instance inside main()
        Child child = new Child();
        child.helper();
    }
}
```

**输出**

```
2021
Its 2021 !!
geeksforgeeks
```

> **注意:**从上面的输出可以看出，我们已经成功地直接访问了受保护的成员，因为这些成员是由 Child 类继承的，并且可以在不使用任何引用的情况下访问。受保护的成员由子类继承，并且可以作为自己的成员访问它们。但是我们不能使用父类的引用来访问这些成员。我们只能通过使用子类引用来访问受保护的成员。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate Compile-time Error Thrown
// When we are Trying to Access Protected Members
// Using Parent Class Reference

// Importing packages
package package2;
import package1.Sample;

// Importing class extending to Parent class
public class Child extends Sample {

    // Method 1
    void helper()
    {
        // Creating instance of Child class inside main()
        Child myself = new Child();

        // As Child is sub-class of Sample, we can access
        // the static variable here
        System.out.println(Sample.title);

        // This will compile fine as we are accessing year
        // using child class reference variable
        System.out.println(year);
        System.out.println(myself.year);

        // This will compile fine as we are accessing
        // printYear() method using child class reference
        // variable
        printYear();
        myself.printYear();

        // Creating parent class object
        Sample sample = new Sample();

        // Parent class reference holding child class object
        Sample child = new Child();

        // Note: Below lines of code won't compile as we are
        // trying to access protected members of parent
        // class using Parent's class reference which is
        // present in other package

        // Errors will be thrown
        System.out.println(sample.year);
        sample.printYear();
        child.printYear();
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Creating child class instance inside main()
        Child child = new Child();

        // Calling the above method 1 of child class
        child.helper();
    }
}
```

**输出**

```
error: year has protected access in Sample
        System.out.println(sample.year); 
                                 ^
error: printYear() has protected access in Sample
        sample.printYear(); 
              ^
error: printYear() has protected access in Sample
        child.printYear();
             ^
```

因此，默认访问修饰符和受保护修饰符之间的主要区别是，默认成员只能在当前包中访问。而受保护的成员只能在同一个包中和包外的任何地方访问，并且只能使用子类的引用变量，而不能在父类的引用变量上访问。我们不能使用父类的引用来访问受保护的成员。