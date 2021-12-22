# 我们可以覆盖 Java 中的私有方法吗？

> 原文:[https://www . geesforgeks . org/can-override-private-methods-Java/](https://www.geeksforgeeks.org/can-override-private-methods-java/)

让我们首先考虑下面的 Java 程序，作为重写或运行时多态性的一个简单例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Base {
  public void fun() {
     System.out.println("Base fun");    
  }
}

class Derived extends Base {
  public void fun() {  // overrides the Base's fun()
     System.out.println("Derived fun");    
  }
  public static void main(String[] args) {
      Base obj = new Derived();
      obj.fun();
  } 
}
```

程序打印“衍生的乐趣”。
基类引用‘obj’引用了一个派生类对象(参见表达式“Base obj = new Derived()”)。当在 obj 上调用 fun()时，调用是根据引用对象的类型进行的，而不是根据引用进行的。

***使用私有方法可以覆盖吗？***
预测以下程序的输出。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
class Base {
  private void fun() {
     System.out.println("Base fun");    
  }
}

class Derived extends Base {
  private void fun() {
     System.out.println("Derived fun");    
  }
  public static void main(String[] args) {
      Base obj = new Derived();
      obj.fun();
  } 
}
```

我们得到编译器错误“fun()在 Base 中有私有访问权”(参见[本](http://ideone.com/arKk3c))。所以编译器尝试调用基类函数，而不是派生类，意味着 fun()没有被重写。

***一个内部类可以访问其外部类的私有成员。如果我们扩展一个内部类并在内部类中创造乐趣()会怎么样？***
一个内部类可以访问其外部类的私有成员，例如在下面的程序中， *fun()* 的*内部*访问私有数据成员 *msg* ，这被编译器罚款。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/* Java program to demonstrate whether we can override private method
   of outer class inside its inner class */
class Outer {
     private String msg = "GeeksforGeeks";
     private void fun() {
          System.out.println("Outer fun()");
     }

     class Inner extends Outer {
         private void fun()  {
               System.out.println("Accessing Private Member of Outer: " + msg);
         }
     }

     public static void main(String args[])  {

          // In order to create instance of Inner class, we need an Outer
          // class instance. So, first create Outer class instance and then
          // inner class instance.
          Outer o = new Outer();
          Inner  i   = o.new Inner();

          // This will call Inner's fun, the purpose of this call is to
          // show that private members of Outer can be accessed in Inner.
          i.fun(); 

          // o.fun() calls Outer's fun (No run-time polymorphism).
          o = i;
          o.fun();
     }
}
```

输出:

```java
Accessing Private Member of Outer: GeeksforGeeks
Outer fun()
```

在上面的程序中，我们创建了一个外部类和一个内部类。我们从外部扩展了内部，并在外部和内部创建了一个有趣的方法()。如果我们观察我们的输出，那么很明显 fun()方法没有被覆盖。之所以如此，是因为 ***私有方法是在编译时绑定的，决定调用什么方法的是引用变量的类型——而不是它引用的对象的类型。*** 。顺便提一下，由于静态绑定，私有方法在性能方面可能更好(与非私有和非最终方法相比)。

***与 C++的比较***
**【1)**在 Java 中，允许内部类访问外部类的私有数据成员。这个行为和 C++一样(见[这个](https://www.geeksforgeeks.org/nested-classes-in-c/))。
**2)** 在 Java 中，声明为私有的方法永远不能被覆盖，事实上它们在编译时是有界的。这种行为不同于 C++。在 C++中，我们可以有虚拟私有方法(参见[这个](http://ideone.com/6645Uz))。
本文由 [**钱德拉·普拉卡什**](https://www.facebook.com/chandra.prakash.52643) 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。