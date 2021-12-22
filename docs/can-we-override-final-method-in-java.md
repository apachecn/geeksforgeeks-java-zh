# 我们可以覆盖 Java 中的 Final 方法吗？

> 原文:[https://www . geesforgeks . org/can-we-override-final-method-in-Java/](https://www.geeksforgeeks.org/can-we-override-final-method-in-java/)

子类中的方法被称为[**覆盖其超类中的方法，如果该方法具有与其超类中的方法相同的签名。当子类的对象调用这个方法时，总是会调用被覆盖的版本。换句话说，在超类中被覆盖的方法将被隐藏。**](https://www.geeksforgeeks.org/overriding-in-java/)

[JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 有两个选择，它可以调用超类中的原始方法，也可以调用子类中的被覆盖方法。由于后期绑定，这个决定是在运行时而不是编译时做出的。

**我们可以覆盖最终方法吗？**

不，声明为最终的方法不能被覆盖或隐藏。正是因为这个原因，只有当我们确定一个方法是完整的时，它才必须被声明为最终的。

*   值得注意的是[抽象方法](https://www.geeksforgeeks.org/abstract-methods-in-java-with-examples/)不能被声明为最终的，因为它们不完整，覆盖它们是必要的。
*   方法在 java 中被声明为 final，以防止子类重写它们并改变它们的行为，本文的最后将讨论这一点。
*   final 关键字的优点是，它阻止开发人员有意或无意地更改出于安全或其他原因不应更改的方法的行为。

**覆盖最终方法的结果**

在下面的代码中:

*   IntegralOperations 类有两种方法，执行预期操作的加法和减法。
*   加法和减法都被宣布为最终结果。
*   子类扩展了积分运算，并试图覆盖加减运算。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate result of overriding a final
// method

class IntegralOperations {

    // add declared as final
    final int add(int a, int b) { return a + b; }

    // subtract declared as final
    final int subtract(int a, int b) { return a - b; }
}

class child extends IntegralOperations {

    // try to override add
    @Override int add(int a, int b) { return a - b; }

    // try to override subtract
    @Override int subtract(int a, int b) { return a * b; }
}

public class Main {
    public static void main(String[] args)
    {
        child c1 = new child();
        System.out.println(c1.add(1, 4));
    }
}
```

**输出**

```java
prog.java:13: error: add(int,int) in child cannot override add(int,int) in IntegralOperations
    @Override int add(int a, int b) { return a - b; }
                  ^
  overridden method is final
prog.java:16: error: subtract(int,int) in child cannot override subtract(int,int) in IntegralOperations
    @Override int subtract(int a, int b) { return a * b; }
                  ^
  overridden method is final
2 errors
```

> **从上面的输出可以明显看出，试图覆盖最终方法会导致编译时错误。**
> **这证明了最终的方法在 Java 中是不能被覆盖的。**

**为什么最终关键字阻止覆盖？**

一开始，讨论了要被覆盖的方法遵循 [**【动态方法调度】**](https://www.geeksforgeeks.org/dynamic-method-dispatch-runtime-polymorphism-java/) (后期绑定)但是被声明为最终的方法遵循 [**【静态绑定】**](https://www.geeksforgeeks.org/static-vs-dynamic-binding-in-java/#:~:text=Static%20Binding%3A%20The%20binding%20which,is%20done%20at%20compile%2Dtime%20.) (前期绑定)，这意味着方法定义本身将在编译时被分组为一个体。

换句话说，JVM 必须确切知道在编译时调用哪个方法。为了实现这一点，对于每个最终的方法定义，必须有一个唯一的主体。但是如果允许覆盖，那么一个方法定义可以有多个主体，那么编译器将无法选择其中的一个。

这个问题可以在上面的例子中看到，在这个例子中，我们有两个体，每个体用于加法和减法。这会提示编译器在编译时引发错误。这样，final 关键字防止重写并保护方法的语义。