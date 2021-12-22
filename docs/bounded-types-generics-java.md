# Java 中带有泛型的有界类型

> 原文:[https://www.geeksforgeeks.org/bounded-types-generics-java/](https://www.geeksforgeeks.org/bounded-types-generics-java/)

有时，您可能希望限制可在参数化类型中用作类型参数的类型。例如，对数字进行操作的方法可能只想接受数字或其子类的实例。这就是有界类型参数的用途。

*   Sometimes we don't want the whole class to be parameterized. In this case, we can create a Java [generic](https://www.geeksforgeeks.org/generics-in-java/) method. Because the constructor is a special method, we can also use generic types in the constructor.
*   Suppose we want to limit the object types that can be used in parameterized types. For example, in a method of comparing two objects, we want to ensure that the accepted objects are comparable.
*   These methods are called similarly to unbounded methods, except that if we try to use any incomparable classes, it will throw a compile-time error.

**如何在 Java 中声明有界类型参数？**

1.  Lists the names of type parameters,
2.  Unicom extends keyword
3.  And arranged according to its upper limit. (In the following example, c is **a** . )

**语法**

```java
<T extends superClassName>
```

注意，在这个上下文中，extends 一般用于表示“extends”(如在类中)。此外，这指定 T 只能被超类名或超类名的子类替换。因此，超类定义了一个包含性的上限。

**让我们举一个如何用泛型实现有界类型(扩展超类)的例子。**

## Java

```java
// This class only accepts type parametes as any class
// which extends class A or class A itself.
// Passing any other type will cause compiler time error

class Bound<T extends A>
{

    private T objRef;

    public Bound(T obj){
        this.objRef = obj;
    }

    public void doRunTest(){
        this.objRef.displayClass();
    }
}

class A
{
    public void displayClass()
    {
        System.out.println("Inside super class A");
    }
}

class B extends A
{
    public void displayClass()
    {
        System.out.println("Inside sub class B");
    }
}

class C extends A
{
    public void displayClass()
    {
        System.out.println("Inside sub class C");
    }
}

public class BoundedClass
{
    public static void main(String a[])
    {

        // Creating object of sub class C and
        // passing it to Bound as a type parameter.
        Bound<C> bec = new Bound<C>(new C());
        bec.doRunTest();

        // Creating object of sub class B and
        // passing it to Bound as a type parameter.
        Bound<B> beb = new Bound<B>(new B());
        beb.doRunTest();

        // similarly passing super class A
        Bound<A> bea = new Bound<A>(new A());
        bea.doRunTest();

    }
}
```

**输出**

```java
Inside sub class C
Inside sub class B
Inside super class A
```

现在，我们只限于类型 A 和它的子类，所以它会为任何其他类型的子类抛出一个错误。

## 爪哇

```java
// This class only accepts type parametes as any class
// which extends class A or class A itself.
// Passing any other type will cause compiler time error

class Bound<T extends A>
{

    private T objRef;

    public Bound(T obj){
        this.objRef = obj;
    }

    public void doRunTest(){
        this.objRef.displayClass();
    }
}

class A
{
    public void displayClass()
    {
        System.out.println("Inside super class A");
    }
}

class B extends A
{
    public void displayClass()
    {
        System.out.println("Inside sub class B");
    }
}

class C extends A
{
    public void displayClass()
    {
        System.out.println("Inside sub class C");
    }
}

public class BoundedClass
{
    public static void main(String a[])
    {
        // Creating object of sub class C and
        // passing it to Bound as a type parameter.
        Bound<C> bec = new Bound<C>(new C());
        bec.doRunTest();

        // Creating object of sub class B and
        // passing it to Bound as a type parameter.
        Bound<B> beb = new Bound<B>(new B());
        beb.doRunTest();

        // similarly passing super class A
        Bound<A> bea = new Bound<A>(new A());
        bea.doRunTest();

        Bound<String> bes = new Bound<String>(new String());
        bea.doRunTest();
    }
}
```

**输出:**

```java
error: type argument String is not within bounds of type-variable T
```

### **多重界限**

有界类型参数可以与方法以及类和接口一起使用。

Java 泛型也支持多边界，也就是说，在这种情况下，A 可以是一个接口或类。如果 A 是类，那么 B 和 C 应该是接口。我们不能在多个范围内有一个以上的类。

**语法:**

```java
<T extends superClassName & Interface>
```

## Java

```java
class Bound<T extends A & B>
{

    private T objRef;

    public Bound(T obj){
        this.objRef = obj;
    }

    public void doRunTest(){
        this.objRef.displayClass();
    }
}

interface B
{
    public void displayClass();
}

class A implements B
{
    public void displayClass()
    {
        System.out.println("Inside super class A");
    }
}

public class BoundedClass
{
    public static void main(String a[])
    {
        //Creating object of sub class A and
        //passing it to Bound as a type parameter.
        Bound<A> bea = new Bound<A>(new A());
        bea.doRunTest();

    }
}
```

**输出**

```java
Inside super class A
```

本文由 [**Saket Kumar**](https://github.com/saketkumar95) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org/)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。