# 匿名内部类和 Lambda 表达式的区别

> 原文:[https://www . geeksforgeeks . org/区别-匿名-内部类-和-lambda-表达式/](https://www.geeksforgeeks.org/difference-between-anonymous-inner-class-and-lambda-expression/)

### [匿名内部类](https://www.geeksforgeeks.org/anonymous-inner-class-java/):

它是一个没有名称的内部类，并且只为其创建了一个对象。匿名内部类在创建具有某些“额外功能”的对象实例时非常有用，例如重载类或接口的方法，而不必实际子类化类。
匿名内部类在为图形编程中的侦听器接口编写实现类时非常有用。
匿名内部类主要有两种创建方式:

*   [类](https://www.geeksforgeeks.org/classes-objects-java/)(可能是[抽象或具体](https://www.geeksforgeeks.org/difference-between-abstract-class-and-concrete-class-in-java/))
*   [界面](https://www.geeksforgeeks.org/interfaces-in-java/)

**语法:**匿名类表达式的语法类似于构造函数的调用，只是代码块中包含一个类定义。

```
// Test can be interface, abstract/concrete class
Test t = new Test() 
{
   // data members and methods
   public void test_method() 
   {
      ........
      ........
    }   
};
```

为了理解匿名内部类，我们来看一个简单的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the need for Anonymous Inner class

interface Age {
    int x = 21;
    void getAge();
}

class AnonymousDemo {
    public static void main(String[] args)
    {
        // Myclass is implementation class of Age interface
        MyClass obj = new MyClass();

        // calling getage() method implemented at Myclass
        obj.getAge();
    }
}

// Myclass implement the methods of Age Interface
class MyClass implements Age {
    @Override
    public void getAge()
    {
        // printing the age
        System.out.print("Age is " + x);
    }
}
```

**Output:** 

```
Age is 21
```

### [λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/):

Lambda 表达式基本表达[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)的实例(单一抽象方法的接口称为功能接口。一个例子是 java.lang.Runnable)。lambda 表达式实现了唯一的抽象函数，因此实现了功能接口
lambda 表达式是在 Java 8 中添加的，并提供了以下功能。

*   允许将功能视为方法参数，或将代码视为数据。
*   一种可以不属于任何类而创建的函数。
*   lambda 表达式可以像对象一样传递，并按需执行。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate lambda expressions
// to implement a user defined functional interface.

// A sample functional interface (An interface with
// single abstract method
interface FuncInterface {
    // An abstract function
    void abstractFun(int x);

// A non-abstract (or default) function
default void
    normalFun()
    {
        System.out.println("Hello");
    }
}

class Test {
    public static void main(String args[])
    {
        // lambda expression to implement above
        // functional interface. This interface
        // by default implements abstractFun()
        FuncInterface fobj = (int x) -> System.out.println(2 * x);

        // This calls above lambda expression and prints 10.
        fobj.abstractFun(5);
    }
}
```

**Output:** 

```
10
```

### 差异表:

<figure class="table">

| 匿名内部类 | λ表达式 |
| --- | --- |
| 这是一个没有名字的班级。 | 这是一个没有名字的方法。(匿名函数) |
| 它可以扩展抽象类和具体类。 | 它不能扩展抽象和具体的类。 |
| 它可以实现包含任意数量抽象方法的接口。 | 它可以实现一个包含单个抽象方法的接口。 |
| 在这里面我们可以声明实例变量。 | 它不允许声明实例变量，无论声明的变量只是作为局部变量。 |
| 匿名内部类可以被实例化。 | 无法实例化 Lambda 表达式。 |
| 在匿名内部类中，“this”总是指当前的匿名内部类对象，而不是外部对象。 | 在 Lambda 表达式中，“this”总是指当前的外部类对象，即封闭类对象。 |
| 如果我们想处理多种方法，这是最好的选择。 | 如果我们想处理接口，这是最好的选择。 |
| 在编译时，一个单独的。将生成类文件。 | 在编译的时候，没有单独的。将生成类文件。它只是将其转换为私有方法外部类。 |
| 每当我们创建对象时，内存分配都是按需的。 | 它驻留在 JVM 的永久内存中。 |

</figure>