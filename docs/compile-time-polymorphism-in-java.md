# Java 中的编译时多态性

> 原文:[https://www . geesforgeks . org/编译时-java 多态性/](https://www.geeksforgeeks.org/compile-time-polymorphism-in-java/)

[**多态性**](https://www.geeksforgeeks.org/polymorphism-in-java/) 在 Java 中指的是一个对象采取几种形式的能力。多态性允许我们在 Java 中以多种方式执行相同的动作。

**多态性分为两种类型:**

1.  Compile time polymorphism
2.  Runtime polymorphism

> **注:**运行时多态性通过**方法覆盖实现。**而编译时多态性是通过**方法重载**和**运算符重载**实现的。

在本文中，我们将看到编译时多态性。

## **编译时多态性**

编译时多态性也称为静态多态性或早期绑定。编译时多态性是在编译过程中解决的多态性。方法的重载是通过类的引用变量调用的。编译时多态性是通过**方法重载**和**运算符重载实现的。**

### **1。方法重载**

我们可以有一个或多个同名的方法，这些方法只能通过参数编号、类型或顺序来区分。

当一个类有许多同名但不同参数的方法时，就会发生方法重载。如果两个或多个方法具有其他数量的参数、不同的数据类型或不同数量的参数和不同的数据类型，则它们可能具有相同的名称。

**例:**

```java
void gfg() { ... }
void gfg(int num1 ) { ... }
void gfg(float num1) { ... }
void gfg(int num1 , float num2 ) { ... } 
```

#### **(一)。通过改变参数数量的方法重载**

在这种类型中，方法重载是通过用不同数量的参数重载函数调用中的方法来实现的

**例:**

```java
show( char a )
show( char a ,char b )
```

在给定的示例中，第一个 show 方法有一个参数，第二个 show 方法有两个方法。调用函数时，编译器会查看参数的数量，并决定如何解析方法调用。

## 爪哇

T0】输出

```java
number 1 : 3
number 1 : 4  number 2 : 5
```