# Java 中的 instanceof 运算符 vs isInstance()方法

> 原文:[https://www . geesforgeks . org/instance of-operator-vs-is instance-method-in-Java/](https://www.geeksforgeeks.org/instanceof-operator-vs-isinstance-method-in-java/)

运算符的**实例和 **isInstance()** 方法都用于检查对象的类别。但是主要的区别来自于我们想要动态检查对象的类。在这种情况下 **isInstance()** 方法会起作用。我们不可能通过**运算符的**实例来做到这一点。**

运算符的**实例和**实例()**方法都返回布尔值。isInstance()方法是 java 中 class 的一个方法，而 instanceof 是一个运算符。
举个例子:**

```
// Java program to demonstrate working of
// instanceof operator
public class Test
{
    public static void main(String[] args)
    {
        Integer i = new Integer(5);

        // prints true as i is instance of class
        // Integer
        System.out.println(i instanceof Integer);
    }
}
```

输出:

```
true

```

现在如果我们想在运行时检查对象的类，那么我们必须使用 **isInstance()** 方法。

```
// Java program to demonstrate working of isInstance() 
// method 
public class Test 
{ 
    // This method tells us whether the object is an 
    // instance of class whose name is passed as a 
    // string 'c'. 
    public static boolean fun(Object obj, String c) 
                      throws ClassNotFoundException 
    { 
        return Class.forName(c).isInstance(obj); 
    } 

    // Driver code that calls fun() 
    public static void main(String[] args) 
                      throws ClassNotFoundException 
    { 
        Integer i = new Integer(5); 

        // print true as i is instance of class 
        // Integer 
        boolean b = fun(i, "java.lang.Integer"); 

        // print false as i is not instance of class 
        // String 
        boolean b1 = fun(i, "java.lang.String"); 

        /* print true as i is also instance of class 
           Number as Integer class extends Number 
           class*/
        boolean b2 = fun(i, "java.lang.Number"); 

        System.out.println(b); 
        System.out.println(b1); 
        System.out.println(b2); 
    } 
} 
```

输出:

```
true
false
true

```

**注意:**如果我们用其他没有实例化的类检查对象，instanceof 运算符会引发编译时错误(不兼容的条件操作数类型)。

```
public class Test
{
    public static void main(String[] args)
    {
        Integer i = new Integer(5);

        // Below line causes compile time error:-
        // Incompatible conditional operand types
        // Integer and String
        System.out.println(i instanceof String);
    }
}
```

输出:

```
13: error: incompatible types: Integer cannot be converted to String
        System.out.println(i instanceof String);
                           ^
```

**相关文章:**
[Java 中新运算符 vs newInstance()方法](https://www.geeksforgeeks.org/new-operator-vs-newinstance-method-java/)
[Java 中的倒影](https://www.geeksforgeeks.org/reflection-in-java/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。