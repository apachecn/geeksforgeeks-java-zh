# Java 中静态块的构造函数重载

> 原文:[https://www . geeksforgeeks . org/constructor-用静态块重载 java/](https://www.geeksforgeeks.org/constructor-overloading-with-static-block-in-java/)

在 Java 中，[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)是一个代码块，类似于用于初始化对象状态的方法。构造函数在创建对象或实例时被调用。每次使用 **new()** 关键字创建对象时，至少调用一个构造函数(可以是默认构造函数)来为同一类的数据成员分配初始值。

## Java

```
// A Java program to demonstrates Constructor
class Emp {
    int id;
    String name;

    // this would be invoked while an object
    // of that class is created.
    public Emp() { System.out.println("GeeksforGeeks"); }
}

// Driver Code
public class GFG {
    public static void main(String[] args)
    {
        // this would invoke default constructor.
        Emp obj = new Emp();
    }
}
```

**输出**

```
GeeksforGeeks
```

### [构造函数重载](https://www.geeksforgeeks.org/constructor-overloading-java/):

像[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)一样，我们也可以重载构造函数。在构造函数重载中，我们可以用不同的参数创建多个构造函数，有时需要用不同的方式初始化一个对象。这可以使用构造函数重载来完成。

在本例中，我们创建了两个具有相同类名的构造函数，每个构造函数的参数都不同，为了访问构造函数，我们通过对象类传递参数。当我们通过对象类传递值 10 时，调用带有 int 参数的第二个构造函数，如果没有值通过对象类，则调用默认构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrates
// Constructor Overloading
class Emp {

    int id;

    // Default Constructor
    public Emp() // Constructor1
    {
        System.out.println("Default Constructor");
    }

    // Parameterized Constructor
    public Emp(int id)
    {
        System.out.println("Parameterized Constructor");
    }
}

// Driver Code
public class GFG {

    public static void main(String[] args)
    {
        // Accessing parameterized constructor
        Emp obj = new Emp(10);
    }
}
```

**输出:**

```
Parameterized Constructor
```

### 静态块的构造函数重载

Java 中的[静态块](https://www.geeksforgeeks.org/g-fact-79/)用于类的静态初始化。当类加载到内存中时，静态块执行。静态块中的代码只执行一次。静态块也有助于减少代码行。让我们理解为什么在 Java 中需要静态块的构造函数重载。假设一家公司为一个独特的角色开发人员雇佣了一些没有经验或两年经验的员工。由于新聘用的候选人属于开发人员类别，我们可以使用静态块来实现这一点。

## Java

```
// Java program to demonstrates Constructor
// Overloading with static block
class Emp {
    int id, exp;
    String name;
    static String category;

    // Static block with category Developer
    static { category = "Developer"; }

    // Default Constructor
    public Emp()
    {
        System.out.println("-"
                           + "\t"
                           + "-"
                           + "\t"
                           + "-"
                           + "\t"
                           + "\t"
                           + "-");
    }

    // Parameterized Constructor with two arguments
    public Emp(int id, String name)
    {
        System.out.println(id + "\t" + name + "\t"
                           + category + "\t" + exp);
    }

    // Parameterized Constructor with three arguments
    public Emp(int id, String name, int exp)
    {
        System.out.println(id + "\t" + name + "\t"
                           + category + "\t" + exp);
    }
}

// Driver Code
public class GFG {

    public static void main(String[] args)
    {
        System.out.println("Id"
                           + "\t"
                           + "Name"
                           + "\t"
                           + "Category"
                           + "\t"
                           + "Exp");

        // Passing values to parameterized constructor with
        // two arguments
        Emp obj1 = new Emp(1863, "Kumar");

        // Passing values to parameterized constructor with
        // three arguments
        Emp obj2 = new Emp(1864, "ravi", 2);

        // Calling Default COnstructor
        Emp obj3 = new Emp();
    }
}
```

**输出**

```
Id    Name    Category    Exp
1863    Kumar    Developer    0
1864    ravi    Developer    2
-    -    -        -
```

在上面的例子中，在带有两个参数的参数化构造函数中，我们传递了唯一的 id，来自对象的名称，在输出中，我们还可以看到 category 和 exp 也被打印出来，这是因为我们已经为类别 Developer 创建了一个静态块，如果没有值被传递给它，java 会自动分配 0。在带有三个参数的参数化构造函数中，我们只传递 id、name、exp，但是类别也打印在输出中，这是因为类别在静态块中。