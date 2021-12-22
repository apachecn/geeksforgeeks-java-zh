# Java 中关于 null 的有趣事实

> 原文:[https://www . geesforgeks . org/interior-facts-about-null-in-Java/](https://www.geeksforgeeks.org/interesting-facts-about-null-in-java/)

几乎所有的编程语言都与 null 绑定。几乎没有一个程序员不为 null 所困扰。
在 Java 中，null 是关联的 java.lang.NullPointerException，由于它是 java.lang 包中的一个类，所以当我们尝试执行一些有 null 或没有 null 的操作时，就会调用它，有时我们甚至不知道它发生在哪里。

以下是关于 java 中 null 的一些要点，每个 Java 程序员都应该知道:

**1。null 区分大小写:** null 在 java 中是字面意思，因为关键字在 Java 中是**区分大小写的**，所以我们不能像 C 语言那样写 null 或 0。

```java
public class Test
{
    public static void main (String[] args) throws java.lang.Exception
    {
        // compile-time error : can't find symbol 'NULL'
        Object obj = NULL; 

        //runs successfully
        Object obj1 = null; 
    }
}
```

输出:

```java
5: error: cannot find symbol
 can't find symbol 'NULL'
                 ^
   variable NULL
 class Test
1 error 

```

**2。引用变量值:**Java 中任何引用变量都有默认值 null。

```java
public class Test
{
    private static Object obj; 
    public static void main(String args[])
    {
        // it will print null;
        System.out.println("Value of object obj is : " + obj);
    } 
}
```

输出:

```java
Value of object obj is : null 

```

**3。null 的类型:**与常见的误解不同，null 不是 Object 或者既不是类型。这只是一个特殊的值，可以分配给任何引用类型，您可以将空值转换为任何类型
示例:

```java
    // null can be assigned to String
    String str = null; 

    // you can assign null to Integer also
    Integer itr = null; 

    // null can also be assigned to Double
    Double dbl = null; 

    // null can be type cast to String
    String myStr = (String) null; 

    // it can also be type casted to Integer
    Integer myItr = (Integer) null; 

    // yes it's possible, no error
    Double myDbl = (Double) null; 

```

**4。自动装箱和取消装箱:**在自动装箱和取消装箱操作期间，如果将空值赋给基元装箱数据类型，编译器只需抛出空指针异常错误。

```java
public class Test
{
    public static void main (String[] args) throws java.lang.Exception
    {
            //An integer can be null, so this is fine
            Integer i = null;

            //Unboxing null to integer throws NullpointerException
            int a = i;
    }
}
```

输出:

```java
 Exception in thread "main" java.lang.NullPointerException
    at Test.main(Test.java:6) 

```

**5。instanceof 运算符:**Java instance of 运算符用于测试对象是否是指定类型(类或子类或接口)的实例。在运行时，如果表达式的值不为空，instanceof 运算符的结果为真。
这是 instanceof 操作的一个重要属性，这使得它对于类型转换检查非常有用。

```java
public class Test
{
    public static void main (String[] args) throws java.lang.Exception
    {
        Integer i = null;
        Integer j = 10;

        //prints false
        System.out.println(i instanceof Integer);

        //Compiles successfully
        System.out.println(j instanceof Integer);
    }
}
```

输出:

```java
false 
true

```

**6。静态 vs 非静态方法:**我们不能对空值的引用变量调用非静态方法，它会抛出 NullPointerException，但是我们可以对空值的引用变量调用静态方法。因为静态方法是使用静态绑定绑定的，所以它们不会抛出空指针异常。

```java
public class Test
{             
    public static void main(String args[])
    {
        Test obj= null;
        obj.staticMethod();
        obj.nonStaticMethod();                             
    }

    private static void staticMethod()
    {
        //Can be called by null reference
        System.out.println("static method, can be called by null reference");

    }

    private void nonStaticMethod()
    {
        //Can not be called by null reference
        System.out.print(" Non-static method- ");
        System.out.println("cannot be called by null reference");

    }

}
```

输出:

```java
static method, can be called by null referenceException in thread "main" 
java.lang.NullPointerException
    at Test.main(Test.java:5) 

```

**7。==还有！=** 在 Java 中允许用 null 进行比较和不等于运算符。这对于用 java 中的对象检查 null 非常有用。

```java
public class Test
{             
    public static void main(String args[])
    {

    //return true;
    System.out.println(null==null);

    //return false;
    System.out.println(null!=null);

    }
}
```

输出:

```java
true
false

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。