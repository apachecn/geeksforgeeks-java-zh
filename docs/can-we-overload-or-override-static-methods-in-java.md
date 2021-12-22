# 我们可以重载或者覆盖 java 中的静态方法吗？

> 原文:[https://www . geesforgeks . org/can-we-overload-or-override-static-methods-in-Java/](https://www.geeksforgeeks.org/can-we-overload-or-override-static-methods-in-java/)

让我们首先定义重载和覆盖。
[**覆盖**](https://www.geeksforgeeks.org/overriding-in-java/) :覆盖是像 Java 这样的 OOP 语言的一个特性，与运行时多态性有关。子类(或派生类)提供了超类(或基类)中方法的特定实现。
要执行的实现在运行时决定，并根据用于调用的对象做出决定。请注意，两种方法的签名必须相同。详见 Java 中的[覆盖。](https://www.geeksforgeeks.org/overriding-in-java/) [**重载**](https://www.geeksforgeeks.org/overloading-in-java/) :重载也是像 Java 这样的 OOP 语言的一个特性，与编译时(或静态)多态性有关。这个特性允许不同的方法有相同的名称，但是有不同的签名，特别是输入参数的数量和输入参数的类型。请注意，在 C++和 Java 中，[方法不能根据](https://www.geeksforgeeks.org/g-fact-75/)[返回类型重载。](https://www.geeksforgeeks.org/g-fact-75/)
**我们可以重载静态方法吗？**
答案是‘是’。我们可以有两个或多个同名的静态方法，但是输入参数不同。例如，考虑下面的 Java 程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// filename Test.java
public class Test {
    public static void foo() {
        System.out.println("Test.foo() called ");
    }
    public static void foo(int a) {
        System.out.println("Test.foo(int) called ");
    }
    public static void main(String args[])
    {
        Test.foo();
        Test.foo(10);
    }
}
```

**Output**

```java
Test.foo() called 
Test.foo(int) called 
```

**我们可以重载仅通过静态关键字不同的方法吗？**
如果 Java 中的两个方法仅通过 static 关键字不同(参数数量和参数类型相同)，我们就不能重载它们。参见下面的 Java 程序示例。这个行为在 C++中是一样的(参见[这个](https://www.geeksforgeeks.org/function-overloading-in-c/)的第 2 点)。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// filename Test.java
public class Test {
    public static void foo() {
        System.out.println("Test.foo() called ");
    }
    public void foo() { // Compiler Error: cannot redefine foo()
        System.out.println("Test.foo(int) called ");
    }
    public static void main(String args[]) {
        Test.foo();
    }
}
```

**输出:**

```java
Compiler Error, cannot redefine foo()
```

**我们可以覆盖 java 中的静态方法吗？**
我们可以在子类中声明具有相同签名的静态方法，但是它不被认为是覆盖的，因为不会有任何运行时多态性。因此，答案是“不”。
如果派生类定义了与基类中的静态方法具有相同签名的静态方法，则派生类中的方法将被基类中的方法隐藏。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/* Java program to show that if static method is redefined by
   a derived class, then it is not overriding. */

// Superclass
class Base {

    // Static method in base class which will be hidden in subclass
    public static void display() {
        System.out.println("Static or class method from Base");
    }

     // Non-static method which will be overridden in derived class
     public void print()  {
         System.out.println("Non-static or Instance method from Base");
    }
}

// Subclass
class Derived extends Base {

    // This method is hidden by display() in Base
    public static void display() {
         System.out.println("Static or class method from Derived");
    }

    // This method overrides print() in Base
    public void print() {
         System.out.println("Non-static or Instance method from Derived");
   }
}

// Driver class
public class Test {
    public static void main(String args[ ])  {
       Base obj1 = new Derived();

       // As per overriding rules this should call to class Derive's static
       // overridden method. Since static method can not be overridden, it
       // calls Base's display()
       obj1.display(); 

       // Here overriding works and Derive's print() is called
       obj1.print();    
    }
}
```

**Output**

```java
Static or class method from Base
Non-static or Instance method from Derived
```

以下是 Java 中方法重写和静态方法的一些要点。
**1)** 对于类(或静态)方法，是根据引用的类型调用方法，而不是根据被引用的对象，这意味着方法调用是在编译时决定的。
**2)** 对于实例(或非静态)方法，方法的调用是根据被引用对象的类型，而不是根据引用的类型，这意味着方法调用是在运行时决定的。
**3)** 实例方法不能覆盖静态方法，静态方法不能隐藏实例方法。例如，以下程序有两个编译器错误。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/* Java program to show that if static methods are redefined by
   a derived class, then it is not overriding but hidding. */

// Superclass
class Base {

    // Static method in base class which will be hidden in subclass
    public static void display() {
        System.out.println("Static or class method from Base");
    }

     // Non-static method which will be overridden in derived class
     public void print()  {
         System.out.println("Non-static or Instance method from Base");
    }
}

// Subclass
class Derived extends Base {

    // Static is removed here (Causes Compiler Error)
    public void display() {
        System.out.println("Non-static method from Derived");
    }

    // Static is added here (Causes Compiler Error)
    public static void print() {
        System.out.println("Static method from Derived");
   }
}
```

**4)** 在子类(或派生类)中，我们可以重载从超类继承的方法。这样的重载方法既不隐藏也不覆盖超类方法——它们是新方法，对于子类是唯一的。

**参考文献:**
[http://docs . Oracle . com/javase/tutorial/Java/Iandi/override . html](http://docs.oracle.com/javase/tutorial/java/IandI/override.html)
本文由 [**钱德拉·普拉卡什**](https://www.facebook.com/chandra.prakash.52643?fref=ts) 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。