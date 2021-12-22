# Java 中的嵌套接口

> 原文:[https://www . geesforgeks . org/interface-nested-class-other-interface/](https://www.geeksforgeeks.org/interface-nested-class-another-interface/)

我们可以将接口声明为一个类或另一个接口的成员。这样的接口称为成员接口或嵌套接口。

**类中的接口**
接口(或类)在任何其他类之外声明时只能有公共和默认的访问说明符(详情参见[本](https://www.geeksforgeeks.org/g-fact-81/))。在类中声明的这个接口可以是默认的、公共的、受保护的，而不是私有的。在实现接口时，我们提到的接口是 **c_name.i_name** ，其中 **c_name** 是它所嵌套的类的名称， **i_name** 是接口本身的名称。
让我们看看下面的代码:-

```java
// Java program to demonstrate working of
// interface inside a class.
import java.util.*;
class Test
{
    interface Yes
    {
        void show();
    }
}

class Testing implements Test.Yes
{
    public void show()
    {
        System.out.println("show method of interface");
    }
}

class A
{
    public static void main(String[] args)
    {
        Test.Yes obj;
        Testing t = new Testing();
        obj=t;
        obj.show();
    }
}
```

```java
show method of interface 
```

上例中的访问说明符是默认的。我们还可以分配公共的、受保护的或私有的。下面是一个受保护的例子。在这个特殊的例子中，如果我们将访问说明符改为 private，我们会得到编译器错误，因为一个派生类试图访问它。

```java
// Java program to demonstrate protected 
// specifier for nested interface.
import java.util.*;
class Test
{
    protected interface Yes
    {
        void show();
    }
}

class Testing implements Test.Yes
{
    public void show()
    {
        System.out.println("show method of interface");
    }
}

class A
{
    public static void main(String[] args)
    {
        Test.Yes obj;
        Testing t = new Testing();
        obj=t;
        obj.show();
    }
}
```

```java
show method of interface 
```

**另一个接口中的接口**
一个接口也可以在另一个接口中声明。我们将接口称为 **i_name1.i_name2** ，其中 **i_name1** 是其嵌套的接口的名称， **i_name2** 是要实现的接口的名称。

```java
// Java program to demonstrate working of 
// interface inside another interface.
import java.util.*;
interface Test
{
   interface Yes
   {
      void show();    
   }
}

class Testing implements Test.Yes
{
   public void show()
   {
      System.out.println("show method of interface");
   } 
} 

class A
{
   public static void main(String[] args)
   {
     Test.Yes obj;
     Testing t = new Testing();
     obj = t;
     obj.show();
   } 
}
```

```java
show method of interface 
```

**注意:**在上面的例子中，即使我们没有写 public，访问说明符也是 public。如果我们试图将接口的访问说明符更改为公共以外的任何内容，我们会得到编译器错误。记住，[界面成员只能公开。](https://www.geeksforgeeks.org/g-fact-73/)。

```java
// Java program to demonstrate an interface cannot
// have non-public member interface.
import java.util.*;
interface Test
{
    protected interface Yes
    {
        void show();
    }
}

class Testing implements Test.Yes
{
    public void show()
    {
        System.out.println("show method of interface");
    }
}

class A
{
    public static void main(String[] args)
    {
        Test.Yes obj;
        Testing t = new Testing();
        obj = t;
        obj.show();
    }
}
```

```java
illegal combination of modifiers: public and protected
   protected interface Yes
```

本文由**闪烁泰亚吉**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论