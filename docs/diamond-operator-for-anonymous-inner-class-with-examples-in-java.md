# 匿名内部类的菱形运算符，示例在 Java 中

> 原文:[https://www . geeksforgeeks . org/diamond-operator-for-anonymous-inner-class-with-examples-in-Java/](https://www.geeksforgeeks.org/diamond-operator-for-anonymous-inner-class-with-examples-in-java/)

**先决条件:** [匿名内班](https://www.geeksforgeeks.org/anonymous-inner-class-java/)

**钻石操作符**:钻石操作符是在 Java 7 中作为一个新特性引入的。菱形运算符的主要目的是在创建对象时简化泛型的使用。它避免了程序中未经检查的警告，并使程序更可读。钻石运算符不能用于 JDK 7 中的匿名内部类。在 JDK 9 中，它可以与[匿名类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)一起使用，以简化代码并提高可读性。在 JDK 7 之前，我们必须在表达式的两侧创建一个泛型类型的对象，如下所示:

```java
// Here we mentioned the generic type
// on both side of expression while creating object
List<String> geeks = new ArrayList<String>();

```

当在 Java 7 中引入 Diamond 运算符时，我们可以在表达式右侧创建对象，而无需提及泛型类型，如下所示:

```java
List<String> geeks = new ArrayList<>();

```

**JDK 7 号钻石操作员问题？**

在 Diamond 操作符的帮助下，我们可以创建一个对象，而不用在表达式的右侧提到泛型类型。但问题是它只能在正常的课堂上使用。假设您想对匿名内部类使用 diamond 运算符，那么编译器将抛出如下错误消息:

```java
// Program to illustrate the problem
// while linking diamond operator
// with an anonymous inner class

abstract class Geeksforgeeks<T> {
    abstract T add(T num1, T num2);
}

public class Geeks {
    public static void main(String[] args)
    {
        Geeksforgeeks<Integer> obj = new Geeksforgeeks<>() {
            Integer add(Integer n1, Integer n2)
            {
                return (n1 + n2);
            }
        };
        Integer result = obj.add(10, 20);
        System.out.println("Addition of two numbers: " + result);
    }
}
```

**输出:**

```java
prog.java:9: error: cannot infer type arguments for Geeksforgeeks
        Geeksforgeeks  obj = new Geeksforgeeks  () {
                                                        ^
  reason: cannot use '' with anonymous inner classes
  where T is a type-variable:
    T extends Object declared in class Geeksforgeeks
1 error

```

Java developer 在 JDK 9 中扩展了 diamond 运算符的功能，允许 diamond 运算符也用于匿名内部类。如果我们用 JDK 9 运行上面的代码，那么代码将运行良好，我们将生成下面的输出。

**输出:**

```java
Addition of two numbers: 30

```