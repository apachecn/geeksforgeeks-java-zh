# 我们可以覆盖 Java 中的默认方法吗？

> 原文:[https://www . geesforgeks . org/can-we-override-default-method-in-Java/](https://www.geeksforgeeks.org/can-we-override-default-method-in-java/)

[Java 中的缺省方法](https://www.geeksforgeeks.org/default-methods-java/)是 Java 中的一种方法，在接口内部用关键字 Default 定义的方法称为缺省方法。这是一种非抽象方法。

这个方法能够增加向后能力，这样旧的接口就可以掌握 lambda 表达式的能力。

Java 接口默认方法也称为 Defender 方法或虚拟扩展方法。

在 Java 8 之前，接口只能有抽象方法。这些类分别提供这些方法的实现。所以，如果一个新的方法被添加到一个接口中，那么它的实现代码必须在实现相同接口的类中提供。为了克服这个问题，Java 8 引入了默认方法的概念，允许接口拥有实现方法 ，而不影响实现接口的类。

**我们可以覆盖 Java 中的默认方法吗？**

在 Java 中，重写默认方法并不是强制性的。

如果我们在一个程序中只使用一个界面**，那么我们每次只使用一个默认方法，此时不需要覆盖，如下程序所示:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Creating Interface
interface  GfG{

   public default void display() {
      System.out.println("GEEKSFORGEEKS");
   }
}

// Main Class With Implementation Of Interface
public class InterfaceExample implements GfG{
   public static void main(String args[]) {
      InterfaceExample obj = new InterfaceExample();

      // Calling Interface
      obj.display(); 
   }
}
```

****Output**

```
GEEKSFORGEEKS
```** 

**但是当使用的**多于** **两个接口**并且两个接口都作为父类时，这时需要覆盖默认方法。如果我们使用多个接口并且在两个接口中，如果两个接口具有相同的名称和相同的结构。所以在那个时候，必须重写缺省方法中的任何一个，否则会导致错误。**

****情况 1:当两个接口未被覆盖时****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the case when 
// two interfaces are not overridden

// Creating Interface One
interface GfG{
   public default void display() {
      System.out.println("GEEKSFORGEEKS");
   }
}

// Creating Interface Two
interface gfg{

   public default void display() {
      System.out.println("geeksforgeeks");
   }
}

// Interfaces are not Overidden 
public class InterfaceExample implements GfG,gfg {
   public static void main(String args[])
   {
      InterfaceExample obj = new InterfaceExample();
      obj.display();
   }
}
```

****输出:****

```
InterfaceExample.java:18: error: types GfG and gfg are incompatible;
public class InterfaceExample implements GfG,gfg {
       ^
  class InterfaceExample inherits unrelated defaults for display() from types GfG and gfg
1 error
```

****情况 2:当两个接口被覆盖时****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate the case
// when two interfaces are overridden

// Creating Interface One
interface GfG{
   public default void display()
   {
      System.out.println("GEEKSFORGEEKS");
   }
}

// Creating Interface Two
interface gfg{

   public default void display() 
   {
      System.out.println("geeksforgeeks");
   }
}

public class InterfaceExample implements GfG,gfg {

// Interfaces are Overrided
public void display() {

      GfG.super.display();

      gfg.super.display();
   }

public static void main(String args[]) {
      InterfaceExample obj = new InterfaceExample();
      obj.display();
   }
}
```

****Output**

```
GEEKSFORGEEKS
geeksforgeeks
```**