# 我们能用 Java 实例化一个抽象类吗？

> 原文:[https://www . geesforgeks . org/can-we-instance-a-abstract-class-in-Java/](https://www.geeksforgeeks.org/can-we-instantiate-an-abstract-class-in-java/)

[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)我们听说过，抽象类是可以有抽象方法，不能实例化的类。我们不能在 Java 中实例化抽象类，因为它是抽象的，不完整，因此不能使用。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate abstract class
// cannot have instance

public abstract class ClassOne {

    public void printSomething()
    {
        System.out.println("Hello in abstract class");
    }
}
class CreateClassOne {

    public static void main(String[] args)
    {
        // instance of abstract 
          // class "ClassOne"
        ClassOne obj = new ClassOne();
    }
}
```

**输出**

```java
prog.java:17: error: ClassOne is abstract; cannot be instantiated
        ClassOne obj = new ClassOne();
                       ^
1 error
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// Anonymous class

public abstract class ClassOne {

    public void printSomething()
    {
        System.out.println("Hello in abstract class");
    }
}

class InheritClassOne {

    public static void main(String[] args)
    {

        // obj points to anonymous subclass
        ClassOne obj = new ClassOne() {};

          // calls the implementation 
          // provided by ClassOne
        obj.printSomething();
    }
}
```

**Output**

```java
Hello in abstract class
```

**这里是抽象类实例化！** **但这不可能！**

是的，答案仍然是一样的，抽象类不能被实例化，在第二个例子中，类 1 的对象没有被创建，而是抽象类的一个**匿名子类**的实例。然后你调用方法 ***printSomething()*** 在抽象类引用上指向子类对象 obj。当你在创建第二类对象时添加了 **{ }** ，编译器将其作为匿名类，其中 **{ }** 表示[匿名类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)的主体。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java program to demonstrate anonymous class

interface NewClass {
    public void show();
}

class AnonymousClassExample {

    public static void main(String[] args)
    {
        // nc points to anonymous class inside
        // the {}
        NewClass nc = new NewClass() {
            public void show()
            {
                System.out.println(
                    "This is an anonymous class implementing interface");
            }
        };

        // calls the implementation
        // method of anonymous class
        nc.show();
    }
}
```

**Output**

```java
This is an anonymous class implementing interface
```

在这个例子中，接口没有被实例化，但是一个匿名类正在实现接口 New Class。现在，您可能已经理解了第二个示例是如何工作的，其中创建了一个匿名子类，或者抽象类是由抽象类实现的，而不是抽象类实例化。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Anonymous class implementing abstract class

public abstract class ClassOne {

    public ClassOne()
    {
        System.out.println(
            "Anonymous(Unnamed) Subclass object Created");
    }

    public void printSomething()
    {
        System.out.println(
            "Hello,in abstract class:printSomething method");
    }
    public abstract void implementMethod();
}

class AnonymousClassExample {

    public static void main(String[] args)
    {
        // anonymous class
        ClassOne obj = new ClassOne() {
            @Override public void implementMethod()
            {
                System.out.println(
                    "Implemented abstract method in anonymous class");
            }
        };

        // calls abstract class implementation
        obj.printSomething();

        // calls anonymous class implementation
        obj.implementMethod();
    }
}
```

**Output**

```java
Anonymous(Unnamed) Subclass object Created
Hello,in abstract class:printSomething method
Implemented abstract method in anonymous class
```