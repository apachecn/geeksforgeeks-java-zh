# Java 中编译时和运行时多态性的区别

> 原文:[https://www . geesforgeks . org/Java 中编译时和运行时多态性的区别/](https://www.geeksforgeeks.org/difference-between-compile-time-and-run-time-polymorphism-in-java/)

[多态性](https://www.geeksforgeeks.org/polymorphism-in-java/)这个词的意思是有多种形式。简单地说，我们可以将多态性定义为一条消息以多种形式显示的能力。在本文中，我们将看到两种类型的多态性之间的区别，编译时和运行时。
**编译时多态性:**每当一个对象在编译时与它们的功能绑定在一起，这就是所谓的编译时多态性。在编译时，java 通过检查方法签名知道调用哪个方法。所以这被称为编译时多态性或静态或早期绑定。编译时多态是通过[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)实现的。方法重载表示在一个具有不同原型的类中可以有多个同名的函数。函数重载是实现多态性的方法之一，但它取决于我们采用哪种类型的多态性的技术。在 java 中，我们在编译时实现函数重载。下面是一个可以观察到编译时多态性的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// compile-time polymorphism
public class GFG {

    // First addition function
    public static int add(int a, int b)
    {
        return a + b;
    }

    // Second addition function
    public static double add(
        double a, double b)
    {
        return a + b;
    }

    // Driver code
    public static void main(String args[])
    {
        // Here, the first addition
        // function is called
        System.out.println(add(2, 3));

        // Here, the second addition
        // function is called
        System.out.println(add(2.0, 3.0));
    }
}
```

**Output:** 

```
5
5.0
```

**运行时多态性:**每当对象在运行时与功能绑定时，这被称为运行时多态性。运行时多态可以通过[方法覆盖](https://www.geeksforgeeks.org/overriding-in-java/)来实现。 [Java 虚拟机](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)决定在运行时调用合适的方法，而不是在编译时调用。也称为动态或后期绑定。方法重写表示子类与父类中声明的方法相同。这意味着，如果子类提供了其父类之一所提供的方法的特定实现，那么它就被称为方法重写。下面是一个可以观察到运行时多态性的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// runtime polymorphism

// Implementing a class
class Test {

    // Implementing a method
    public void method()
    {
        System.out.println("Method 1");
    }
}

// Defining a child class
public class GFG extends Test {

    // Overriding the parent method
    public void method()
    {
        System.out.println("Method 2");
    }

    // Driver code
    public static void main(String args[])
    {
        Test test = new GFG();

        test.method();
    }
}
```

**Output:** 

```
Method 2
```

下表演示了运行时多态性和编译时多态性之间的区别:

<figure class="table">

| Sr.No | 编译时多态性 | 运行时多态性 |
| --- | --- | --- |
| one | 在编译时多态性中，调用由编译器解析。 | 在运行时多态性中，编译器不会解析调用。 |
| Two | 它也被称为静态绑定、早期绑定和重载。 | 它也被称为动态绑定、后期绑定和重写。 |
| three | 方法重载是编译时多态性，其中多个方法使用不同的参数或签名以及不同的返回类型共享相同的名称。 | 方法重写是运行时多态性，它具有相同的方法，具有相同的参数或签名，但在不同的类中关联。 |
| four | 它是通过函数重载和运算符重载实现的。 | 它是通过虚函数和指针实现的。 |
| five | 它提供了快速执行，因为需要执行的方法在编译时很早就知道了。 | 与早期绑定相比，它的执行速度较慢，因为需要执行的方法在运行时是已知的。 |
| six | 编译时多态性不太灵活，因为所有事情都是在编译时执行的。 | 运行时多态性更加灵活，因为所有的事情都在运行时执行。 |

</figure>