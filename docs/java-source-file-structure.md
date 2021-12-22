# Java 源文件结构

> 原文:[https://www.geeksforgeeks.org/java-source-file-structure/](https://www.geeksforgeeks.org/java-source-file-structure/)

**Java** 源文件结构描述了 Java 源代码文件必须遵循一个模式或结构。在本文中，我们将看到 Java 程序必须遵循的一些重要准则。

***一个 Java 程序有以下结构:***

**1。** [**包**](https://www.geeksforgeeks.org/packages-in-java/) **语句:**Java 中的包是封装一组类、子包和接口的机制。

**2。导入语句:**导入语句用于导入包、类或接口。

**3。** [**类**](https://www.geeksforgeeks.org/classes-objects-java/) **定义:**类是用户自定义的蓝图或原型，从中创建对象，是被动实体。

### 使用 Java 源文件时需要牢记的要点

以下是我们在使用 Java 时应该记住的几点:

**1。Java 源文件中的类数量:**

一个 Java 程序可以包含任意数量的类，最多可以将其中一个声明为公共类。

**说明:** Java 允许我们在一个程序中创建任意数量的类。但是在所有的类中，最多只能有一个可以声明为公共类。简单地说，程序可以包含零个公共类，或者如果存在公共类，它不能超过一个。

**语句的正确性证明:**让我们在本地 **IDE** 中创建一个程序，在 Javac 编译器**的帮助下进行编译。**

例如在下面的程序中，我们创建了三个空类(极客、学习和编程)。

**源代码:**

## Java

```java
// Declaring classes
class Geeks {

}

class Learning {

}

class Programming {

}
```