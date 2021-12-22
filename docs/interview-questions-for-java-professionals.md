# 【Java 专业人士面试问题

> 原文:[https://www . geesforgeks . org/面试-提问-面向 Java-专业人士/](https://www.geeksforgeeks.org/interview-questions-for-java-professionals/)

**Q1。解释** [**JVM、JRE 和**](https://www.geeksforgeeks.org/differences-jdk-jre-jvm/) **？**
**JVM (Java 虚拟机):** JVM(Java 虚拟机)充当运行 Java 应用的运行时引擎。JVM 实际上是调用 Java 代码中存在的主方法。JVM 是 Java 运行时环境的一部分。
**JRE (Java 运行时环境):** JRE 是指可以执行 Java 字节码的运行时环境。它实现了 JVM (Java 虚拟机)，并提供了 JVM 在运行时使用的所有类库和其他支持文件。所以 JRE 是一个软件包，它包含了运行一个 Java 程序所需要的东西。基本上，它是物理存在的 JVM 的实现。
**JDK(Java 开发工具包):**是编译、文档化、打包 Java 程序的必备工具。JDK 完全包括 JRE，它包含了 Java 程序员的工具。Java 开发工具包是免费提供的。除了 JRE，它还包括解释器/加载器、编译器(javac)、归档器(jar)、文档生成器(javadoc)以及 Java 开发中需要的其他工具。简而言之，它包含 JRE +开发工具。
Q2**。解释公共静态 void main(String args[])。**
**Public:**Public 是访问修饰语。公共意味着任何类都可以访问此方法。
**static :** 它是 java 中的一个关键字，标识它是基于类的，即它可以在不创建类实例的情况下被访问。因为我们希望主方法也在没有任何实例的情况下执行，所以我们使用了 static。
**Void:** 是方法的返回类型。Void 定义了不返回值的方法。
**main:** 这是 JVM 执行的第一个方法。方法的签名必须相同。
**Q3。为什么 Java 是平台无关的？**
平台无关实际上就是“写一次跑哪儿”。Java 之所以这么叫，是因为它的**字节代码**可以在任何系统上运行，而不管它的底层操作系统是什么。
**Q4。为什么 Java 不是纯面向对象的？**
Java 不被认为是纯面向对象的，因为它支持布尔、字节、char、int、float、double、long、short 等原语数据类型。
T43】Q5。定义类和对象。用 java 的例子来解释它们。
**类:**类是用户定义的蓝图或原型，从中创建对象。它表示一种类型的所有对象共有的一组属性或方法。一般来说，类声明可以包括这些组件，顺序为:
**超类(如果有):**类的父类(超类)的名称，如果有，前面加关键字 extends。一个类只能扩展(子类)一个父类。
**接口:**类实现的接口的逗号分隔列表，如果有的话，前面有关键字 implements。一个类可以实现多个接口。
**对象:**是面向对象编程的基本单元，代表现实生活中的实体。一个典型的 Java 程序会创建许多对象，正如您所知，这些对象通过调用方法进行交互。一个对象由:
**状态:**组成，它由一个对象的属性来表示。它还反映了对象的属性。
**行为:**用对象的方法来表示。它还反映了一个对象与其他对象的反应。
**身份:**它为一个对象赋予唯一的名称，并使一个对象能够与其他对象交互。
例如:Employee 是类的例子
具有唯一标识的特定雇员是对象的例子。

```java
class Employee
{
   // instance variables declaration
   // Methods definition
}
```

员工的对象是特定的员工

```java
Employee empObj = new Employee();
```

Employee 的对象之一由‘empObj’
**Q6 指代。什么是方法？提供方法的几个签名**
一个 Java 方法是一组执行任务的语句。方法放在类中。
方法签名:方法的名称、返回类型和参数数量构成了方法签名。
方法的签名中可以有以下元素:
–访问说明符–公共、私有、受保护等。(非强制)
–访问修饰符–静态、同步等。(非强制)
–返回类型–void、int、String 等。(强制)
–方法名–show()(强制)
–带或不带参数–(整数，字符串名)；(括号为必填项)
示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Test {
    void fun1() {}
    public double fun2(double x) {}
    public static void fun3() {}
    public static void fun4(String x) {}
}
```