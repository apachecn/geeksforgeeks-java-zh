# Java 中的功能接口

> 原文:[https://www.geeksforgeeks.org/functional-interfaces-java/](https://www.geeksforgeeks.org/functional-interfaces-java/)

函数接口是只包含一个抽象方法的接口。它们只能展示一种功能。从 Java 8 开始， [lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)可以用来表示函数接口的实例。一个函数接口可以有任意数量的默认方法。*****ActionListener******compatible***是功能接口的一些例子。
在 Java 8 之前，我们必须创建匿名的内部类对象或者实现这些接口。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate functional interface

class Test
{
    public static void main(String args[])
    {
        // create anonymous inner class object
        new Thread(new Runnable()
        {
            @Override
            public void run()
            {
                System.out.println("New thread created");
            }
        }).start();
    }
}
```

****输出:****

```java
New thread created
```

**从 Java 8 开始，我们可以将 [lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)分配给它的函数接口对象，如下所示:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate Implementation of
// functional interface using lambda expressions

class Test
{
  public static void main(String args[])
  {

    // lambda expression to create the object
    new Thread(()->
       {System.out.println("New thread created");}).start();
  }
}
```

```java
New thread created
```

****@FunctionalInterface 注释**
@FunctionalInterface 注释用于保证功能接口不能有多个抽象方法。如果存在多个抽象方法，编译器会标记一个“意外@功能接口注释”消息。但是，并不强制使用此注释。** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate lambda expressions to implement
// a user defined functional interface.

@FunctionalInterface
interface Square
{
    int calculate(int x);
}

class Test
{
    public static void main(String args[])
    {
        int a = 5;

        // lambda expression to define the calculate method
        Square s = (int x)->x*x;

        // parameter passed and return type must be
        // same as defined in the prototype
        int ans = s.calculate(a);
        System.out.println(ans);
    }
}
```

****输出:****

```java
25
```

****java.util.function Package:**
Java 8 中的 Java . util . function Package 包含很多内置的功能接口，比如-** 

*   ****谓词:**谓词接口有一个抽象方法测试，它给出了一个布尔值作为指定参数的结果。它的原型是**

```java
public interface Predicate
{
   public boolean test(T  t);
 }
```

*   ****BinaryOperator:**BinaryOperator 接口有一个抽象方法 apply，该方法接受两个参数并返回相同类型的结果。它的原型是**

```java
public interface BinaryOperator 
{
     public T apply(T x, T y);
} 
```

*   ****函数:**函数接口有一个抽象方法 apply，它接受类型 T 的参数并返回类型 r 的结果。它的原型是**

```java
public interface Function 
{
   public R apply(T t);
}
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// A simple program to demonstrate the use
// of predicate interface
import java.util.*;
import java.util.function.Predicate;

class Test
{
    public static void main(String args[])
    {

        // create a list of strings
        List<String> names =
            Arrays.asList("Geek","GeeksQuiz","g1","QA","Geek2");

        // declare the predicate type as string and use
        // lambda expression to create object
        Predicate<String> p = (s)->s.startsWith("G");

        // Iterate through the list
        for (String st:names)
        {
            // call the test method
            if (p.test(st))
                System.out.println(st);
        }
    }
}
```

****输出:****

```java
Geek
GeeksQuiz
Geek2
```

****重要点/观察:****

1.  **一个函数接口只有一个抽象方法，但它可以有多个默认方法。**
2.  **@FunctionalInterface 注释用于确保一个接口不能有多个抽象方法。该注释的使用是可选的。**
3.  **java.util.function 包包含 Java 8 中的许多内置函数接口。**

**本文由**阿卡什·奥哈**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**