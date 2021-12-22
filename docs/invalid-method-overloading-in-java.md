# Java 中无效的方法重载

> 原文:[https://www . geesforgeks . org/invalid-method-overload-in-Java/](https://www.geeksforgeeks.org/invalid-method-overloading-in-java/)

重载方法是属于同一个类的方法，具有相同的名称但不同的参数。[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)的概念来源于[多态性](https://www.geeksforgeeks.org/difference-between-compile-time-and-run-time-polymorphism-in-java/)。字面上的“聚”意味着很多，“态射”意味着形式。

考虑一个现实生活中的水多态的例子，因为它可以采取多种形式(固体，液体和气体)。同样，在 java 中，我们可以在同一个类中创建多个同名的方法。在这里，我们将讨论 java 中的无效方法重载，但是在此之前，让我们简单地回顾一下方法重载。

**方法重载的条件**

*   我们可以在同一个类中创建多个同名的方法。
*   参数的数量、顺序和类型应该不同。

**说明:**方法重载

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate Method Overloading

// Main class
class GFG {

    // Method 1
    void show()
    {
        // Print statement
        System.out.println("Method to be overloaded.");
    }

    // Method 2
    // Overloading Method 1
    // by changing arguments
    void show(int x)
    {
        // Print statement
        System.out.println("Overloaded method:: 1");
    }

    // Method 3
    // Overloading show method by changing arguments
    void show(String a, int x)
    {
        System.out.println("Overloaded method:: " + x);
    }

    // Method 4
    // Overloading show method
    // by changing arguments
    void show(String a, int b, boolean c)
    {
        System.out.println("Overloaded method:: " + b);
    }

    // Method 5
    // Overloading Method 1 by
    // changing arguments as well as return type
    String show(String s)
    {
        // Print statement
        return "Overloaded method:: 5";
    }

    // Method 6
    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of class inside main()
        GFG obj = new GFG();

        // Calling all methods as defined above
        // to seek overloading concepts
        obj.show();
        obj.show(1);
        obj.show("String", 2);
        obj.show("String", 3, true);
        System.out.println(obj.show("String"));
        obj.show('a');
    }
}
```

**输出-**

```java
Method to be overloaded.
Overloaded method:: 1
Overloaded method:: 2
Overloaded method:: 3
Overloaded method:: 5
Overloaded method:: 1
```

**无效方法重载情况什么时候出现？**

无效方法重载情况的出现是由于以下原因:

1.  如果我们试图调用多个具有相同名称和参数列表的方法。这可以从代码块 1 中证明。
2.  当我们试图仅通过更改返回类型来重载方法时。这可以从代码块 2 中证明。

**实施:**

考虑下面给出的例子。当我们试图调用“ *add(1，2)* ”方法时，编译器会感到困惑，因为没有这样的指令倾向于 int 而不是 double，反之亦然，结果，它会显示一个编译错误。

```java
int add(int a, int b)
double add(int a, int b)
```

**实施例 1-A**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Demo class
class Demo {
    // Programmer defined "mymethod"
    public int myMethod(int num1, int num2)
    {
        System.out.println("First myMethod of class Demo");
        return num1 + num2;
    }
    // Trying to overload "mymethod"
    public int myMethod(int num3, int num4)
    {
        System.out.println("Second myMethod of class Demo");
        return num4 - num3;
    }
}
// Driver class
class GFG {
    // main method
    public static void main(String args[])
    {
        Demo obj1 = new Demo();
        obj1.myMethod(1, 2);
        obj1.myMethod(3, 4);
    }
}
```

**输出:**

```java
prog.java:7: error: method myMethod(int,int) is already defined in class Demo
    public int myMethod(int num3, int num4)
               ^
1 error
```

**例 1-B**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate No Roleplay of Returntype
// Even changed in Method Overloading

// Main class
class GFG {

    int a, b;

    // Declared method
    void add(int x, int y)
    {
        // This refers to current instance itself
        this.a = x;
        this.b = y;

        // Printing the sum
        System.out.println("SUM:: " + (a + b));
    }

    // Method 2
    // To add numbers
    // Overloading the above declared method by
    // changing the return type only
    double add(int x, int y)
    {
        this.a = x;
        this.b = y;
        return a + b;
    }

    // Method 3
    // Main method method
    public static void main(String[] args)
    {
        // Creating object of class inside main()
        GFG obj = new GFG();

        // Calling add() method by passing
        // custom inputs as parameters
        obj.add(5, 2);

        // Trying printing the sum
        System.out.println("Sum:: " + obj.add(3, 4));
    }
}
```

**输出:**

```java
prog.java:8: error: method add(int,int) is already defined in class GFG
  double add(int x,int y){
         ^
prog.java:17: error: 'void' type not allowed here
      System.out.println("Sum:: "+obj.add(3,4));
                                         ^
2 errors
```

> **结论:**我们不能调用多个同名的方法和参数列表。方法的返回类型在方法重载中不起任何作用，在 java 中，仅仅通过改变方法的返回类型是不可能实现重载的。