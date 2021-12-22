# Entrustment and inheritance in Java

> 原文: [https://www .吉斯弗格斯。组织/委托-vs-继承-Java/](https://www.geeksforgeeks.org/delegation-vs-inheritance-java/)

[**Inherit** In Java,](https://www.geeksforgeeks.org/inheritance-in-java/) programming is a process in which one class acquires the attributes of another class. That is, new classes called derived classes or subclasses take over the properties and behaviors of pre-existing classes, which are called base classes or superclasses or parent classes.

**Authorization** means simply transferring a responsibility to others/other things.

*   Delegation can replace inheritance.
*   Delegate means using the object of another class as an instance variable and forwarding the message to the instance.
*   In many cases, it is better than inheritance because it allows you to consider every message you forward, because the instance is of a known class, not of a new class, and because it won't force you to accept all the methods of the superclass: you can only provide truly meaningful methods.
*   Delegate can be regarded as a relationship between objects, in which one object forwards some method calls to another object, which is called its delegate.
*   The main advantage of delegates is the flexibility of runtime-delegates can be easily changed at runtime. But unlike inheritance, delegation is not directly supported by most popular object-oriented languages, and it is not convenient for [dynamic polymorphism](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/) .

```
// Java program to illustrate
// delegation
class RealPrinter {
    // the "delegate"
    void print()
    {
        System.out.println("The Delegate");
    }
}

class Printer {
    // the "delegator"
    RealPrinter p = new RealPrinter();

    // create the delegate
    void print()
    {
        p.print(); // delegation
    }
}

public class Tester {

    // To the outside world it looks like Printer actually prints.
public static void main(String[] args)
    {
        Printer printer = new Printer();
        printer.print();
    }
}
```

Output:

```
The Delegate

```

When you delegate, you just call a class that knows what to do. You don't really care how it is done, what you care about is that the class you call knows what needs to be done.

**Use the same inherited code**

```
// Java program to illustrate
// Inheritance
class RealPrinter {
    // base class implements method
    void print()
    {
        System.out.println("Printing Data");
    }
} 3 // Printer Inheriting functionality of real printer
    class Printer extends RealPrinter {

    void print()
    {
        super.print(); // inside calling method of parent
    }
}

public class Tester {

    // To the outside world it looks like Printer actually prints.
public static void main(String[] args)
    {
        Printer printer = new Printer();
        printer.print();
    }
}
```

Output:

```
Printing Data

```

**When and what to use?**
Here are some examples of using inheritance or entrustment:
Suppose your class is called B, and the derivation/entrustment of the class is called A, then **If**

*   If you want to express the relationship (yes -a), then you want to use inheritance.
*   If you want to be able to pass your class to an existing API that expects A, then you need to use inheritance.
*   You want to enhance A, but A is final and cannot be further subdivided, so you need to use [to synthesize](https://www.geeksforgeeks.org/association-composition-aggregation-java/) and entrust.

This article was contributed by **Abu Shek Gupta** . If you like GeeksforGeeks and want to contribute, you can also use [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) to write an article or mail your article to contribute@geeksforgeeks.org. See your article appear on the homepage of geek blog to help other geeks.

If you find anything incorrect, or you want to share more information about the topics discussed above, please write a comment.