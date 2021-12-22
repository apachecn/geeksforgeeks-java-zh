# Java 中方法内的方法

> 原文:[https://www.geeksforgeeks.org/method-within-method-in-java/](https://www.geeksforgeeks.org/method-within-method-in-java/)

[Java](https://www.geeksforgeeks.org/java/) 不支持**“直接”**嵌套方法。许多函数式编程语言支持方法内的方法。但是您可以在 Java 7 或更旧版本中通过定义本地类来实现嵌套方法功能，类在方法中，因此这确实可以编译。在 java 8 和更新版本中，您可以通过 lambda 表达式来实现。让我们看看它是如何实现的。

**方法 1(使用匿名子类)**
它是一个没有名字的内部类，只为其创建一个对象。匿名内部类在创建具有某些“额外功能”的对象实例时非常有用，例如重载类或接口的方法，而不必实际子类化类。有关匿名内部类[的更多详细信息，请点击此处](https://www.geeksforgeeks.org/anonymous-inner-class-java/)

```java
// Java program implements method inside method
public class GFG {

    // create a local interface with one abstract
    // method run()
    interface myInterface {
        void run();
    }

    // function have implements another function run()
    static void Foo()
    {
        // implement run method inside Foo() function
        myInterface r = new myInterface() {
            public void run()
            {
                System.out.println("geeksforgeeks");
            };
        };
        r.run();
    }
    public static void main(String[] args)
    {
        Foo();
    }
}
```

**Output:**

```java
geeksforgeeks

```

**方法 2(使用局部类)**
你也可以在局部类内部实现一个方法。在方法内部创建的类称为局部内部类。如果要调用本地内部类的方法，必须在方法内部实例化这个类。

```java
// Java program implements method inside method
public class GFG {

    // function have implementation of another 
    // function inside local class
    static void Foo()
    {
        // local class
        class Local {
            void fun()
            {
                System.out.println("geeksforgeeks");
            }
        }
        new Local().fun();
    }
    public static void main(String[] args)
    {
        Foo();
    }
}
```

**Output:**

```java
geeksforgeeks

```

**方法 3(使用一个 lambda 表达式)**
Lambda 表达式基本上表达功能接口的实例(一个具有单一抽象方法的接口称为功能接口。一个例子是 java.lang.Runnable)。lambda 表达式只实现抽象函数，因此实现函数接口。关于表达式[的更多信息，请点击此处](https://www.geeksforgeeks.org/lambda-expressions-java-8/)

```java
// Java program implements method inside method
public class GFG {
    interface myInterface {
        void run();
    }

    // function have implements another function
    // run() using Lambda expression
    static void Foo()
    {
        // Lambda expression
        myInterface r = () ->
        {
            System.out.println("geeksforgeeks");
        };
        r.run();
    }
    public static void main(String[] args)
    {
        Foo();
    }
}
```

**Output:**

```java
geeksforgeeks

```