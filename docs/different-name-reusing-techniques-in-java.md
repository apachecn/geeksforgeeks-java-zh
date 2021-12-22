# Java 中不同的名称重用技术

> 原文:[https://www . geesforgeks . org/different-name-重用-technologies-in-Java/](https://www.geeksforgeeks.org/different-name-reusing-techniques-in-java/)

**覆盖**一个实例方法覆盖超类中所有具有相同签名的可访问实例方法，实现动态调度；换句话说，虚拟机根据实例的运行时类型选择调用哪个重写。重写是面向对象编程的基础，也是通常不鼓励的唯一名称重用形式:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Base Class
class Base {
public void f()
{ }
}

// Derived Class
class Derived extends Base {

// overrides Base.f()
public void f()
{ }
}
```

**隐藏**字段、静态方法或成员类型分别隐藏超类型中具有相同名称(或者，对于方法，签名)的所有可访问字段、静态方法或成员类型。隐藏成员可防止其被继承:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Base class
class Base {
   public static void f()
   { }
}

// Derived class
class Derived extends Base {

   // hides Base.f()
   public static void f()
   { }
}
```

**重载**如果类中的方法具有相同的名称和不同的签名，则它们会相互重载。由调用指定的重载方法在编译时被选择:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Base class
class GeeksForGeeks {

   // int overloading
   public void f(int i)
   { }

   // String overloading
   public void f(String s)
   { }
}
```

**隐藏**一个变量、方法或类型分别隐藏文本封闭范围内同名的所有变量、方法或类型。如果一个实体被遮蔽，你就不能用它的简单名称来引用它；根据实体的不同，您根本无法引用它:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Base class
class GeeksForGeeks {

static String sentence = "I don’t know.";

  public static void main(String[] args) {

     // shadows static field
     String sentence = "I know!";

     // prints local variable
     System.out.println(sentence);
  }
}
```

尽管通常不鼓励阴影，但一个常见的习惯用法确实涉及阴影。构造函数经常重用类中的字段名作为参数名来传递命名字段的值。这个习惯用法并非没有风险，但是大多数 Java 程序员都认为风格上的好处大于风险:

## Java 语言(一种计算机语言，尤用于创建网站)

```
class Shirt {
   private final int size;

   // Parameter shadows Shirt.size
   public Shirt(int size) {
     this.size = size;
   }
}
```

**遮蔽**如果两者都在作用域内，则变量遮蔽同名类型:如果在允许变量和类型的地方使用名称，则引用该变量。类似地，一个变量或一个类型可以隐藏一个包。模糊是唯一一种名称重用，其中两个名称位于不同的名称空间:变量、包、方法或类型。如果一个类型或一个包是模糊的，您不能通过它的简单名称来引用它，除非在语法只允许它的命名空间中有一个名称的上下文中。遵守命名约定在很大程度上消除了模糊

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class Obscure {

  // Obscures type java.lang.System
  static String System;

  public static void main(String[] args) {

     // Next line won’t compile:
     // System refers to static field
     System.out.println("hello, obscure world!");
  }
}
```