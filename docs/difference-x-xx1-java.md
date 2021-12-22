# Java 中 x++和 x=x+1 的区别

> 原文:[https://www.geeksforgeeks.org/difference-x-xx1-java/](https://www.geeksforgeeks.org/difference-x-xx1-java/)

在 x++中，它将 x 的值增加 1，在 x=x+1 中，它也将 x 的值增加 1。但问题是两者是一样的还是有什么区别。我们应该意识到这样一个事实，每当我们试图在两个变量 a 和 b 之间应用任何算术运算符时，结果类型总是 max ( int，a 的类型，b 的类型)。现在让我们看看他们之间的区别:

1.  **Internal Typecasting of data:** In the below example, we are doing arithmetic operation i.e. addition on b and 1\. Here b is of byte type and 1 is of int type. Therefore, the result should be of int type i.e max(int,type of b i.e. byte,type of 1 i.e. int). We are assigning int type to byte type in the above program that’s why we are getting compile time error saying “possible loss precision”. Here typecasting is required to perform addition.

    **使用 x = x + 1**

    ```java
    // Java program to illustrate
    // how arithmetic operations performed
    // depends on data types
    public class Test 
    {
        public static void main(String[] args)
        {
            byte b = 10;

            // Using b = b+1
            b = b + 1;
            System.out.println(b);

            /* Using typecasting will work
            b=(byte)b+1;
            System.out.println(b);*/
        }
    }
    ```

    输出:

    ```java
    error: incompatible types: possible lossy conversion from int to byte

    ```

    使用类型转换，输出将是

    ```java
    11
    ```

    **使用 x++**

    在下一个例子中，我们在做增量，但是在内部我们像 b++一样做操作。结果应该是 int 类型，即 max(int，b 类型，即字节，1 类型，即 int)，我们得到的结果是 11，因为隐式类型转换是由编译器完成的，就像这里的字节 b=(字节)(b+1)。

    ```java
    // Java program to understand the 
    // operations of ++ operator
    public class Test 
    {
        public static void main(String[] args)
        {
        byte b = 10;
        b++;
        System.out.println(b);
        }
    }
    ```

    输出:

    ```java
    11

    ```

    从上面的例子我们可以理解，在递增/递减运算符中，编译器会在需要时自动进行类型转换。但是这是怎么发生的呢？让我们试着理解:
    假设我们必须执行增量，那么我们使用++运算符:

    ```java
    i++;
    ```

    只是一个捷径:

    ```java
    i = i + 1;
    ```

    但是如果我们这样取 I 和 j 的值:

    ```java
    byte i = 1;
    Then i = i + 1;
    ```

    将不会编译，因为我们将 int 值赋给字节类型，而且除了 i++,语句中没有类型转换；会编译好的。
    表示实际上是 i++；是这种事情的捷径

    ```java
    i = (type of i)(i + 1);
    ```

2.  **Different compiler instructions for both :** They are different operators, and use different JVM instructions in bytecode.

    ```java
    x + 1 uses iadd instruction, 
    whereas x++ uses iinc instruction internally
    ```

    虽然这取决于编译器。编译器可以自由地为特定操作使用不同的指令集。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。