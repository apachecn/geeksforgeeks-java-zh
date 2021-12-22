# Java 中 Varargs 的方法重载和歧义

> 原文:[https://www . geeksforgeeks . org/method-overload-diffusion-varargs-Java/](https://www.geeksforgeeks.org/method-overloading-ambiguity-varargs-java/)

先决条件–[变量](https://www.geeksforgeeks.org/variable-arguments-varargs-in-java/)、[方法重载](https://www.geeksforgeeks.org/overloading-in-java/)

**Varargs 中的方法重载**

重载允许不同的方法具有相同的名称，但签名不同，其中签名可能因输入参数的数量或输入参数的类型或两者而异。我们可以通过以下方式重载接受可变长度参数的方法:

*   **Case 1 – Methods with only Varargs parameters:** In this case, Java uses the type difference to determine which overloaded method to call. If one method signature is strictly more specific than the other, then Java chooses it without an error.

    ```
    //Java program to illustrate 
    //method overloading in varargs
    public class varargsDemo
    {
        public static void main(String[] args)
        {
            fun();
        }

        //varargs method with float datatype
        static void fun(float... x)
        {
            System.out.println("float varargs");
        }

        //varargs method with int datatype
        static void fun(int... x)
        {
            System.out.println("int varargs");
        }

        //varargs method with double datatype
        static void fun(double... x)
        {
            System.out.println("double varargs");
        }
    }
    ```

    输出:

    ```
    int varargs

    ```

    这个输出是由于 int 比 double 更具体。如 JLS 部分[15.12.2.5](https://docs.oracle.com/javase/specs/jls/se8/html/jls-15.html#jls-15.12.2.5)中所规定的，如果一个以上的成员方法既可访问又适用于一个方法调用，则有必要选择一个来提供运行时方法分派的描述符。Java 编程语言使用的规则是根据[类型升级](https://www.geeksforgeeks.org/type-conversion-java-examples/)选择最具体的方法。在这种情况下，以下规则定义了基元类型之间的直接超类型关系:

    *   双>浮动
    *   浮动>长
    *   long > int
    *   int > char
    *   int > short
    *   短>字节
*   **Case 2 – Methods with Varargs alongwith other parameters** In this case, Java uses both the number of arguments and the type of the arguments to determine which method to call.

    下面是三次重载 fun()方法的 java 程序:

    ```
    // Java program to demonstrate Varargs 
    // and overloading.
    class Test 
    {
        // A method that takes varargs(here integers).
        static void fun(int ... a) 
        {
            System.out.print("fun(int ...): " +
                    "Number of args: " + a.length +
                    " Contents: ");

            // using for each loop to display contents of a
            for(int x : a)
                System.out.print(x + " ");

            System.out.println();
        }

        // A method that takes varargs(here booleans).
        static void fun(boolean ... a)
        {
            System.out.print("fun(boolean ...) " +
                    "Number of args: " + a.length +
                    " Contents: ");

            // using for each loop to display contents of a
            for(boolean x : a)
                System.out.print(x + " ");

            System.out.println();
        }

        // A method takes string as a argument followed by varargs(here integers).
        static void fun(String msg, int ... a) 
        {
            System.out.print("fun(String, int ...): " +
                    msg + a.length +
                    " Contents: ");

            // using for each loop to display contents of a
            for(int x : a)
                System.out.print(x + " ");

            System.out.println();
        }

        public static void main(String args[])
        {
            // Calling overloaded fun() with different  parameter
            fun(1, 2, 3);
            fun("Testing: ", 10, 20);
            fun(true, false, false);
        }
    }
    ```

    输出:

    ```
    fun(int ...): Number of args: 3 Contents: 1 2 3 
    fun(String, int ...): Testing: 2 Contents: 10 20 
    fun(boolean ...) Number of args: 3 Contents: true false false 

    ```

**变量和歧义**

当重载一个采用可变长度参数的方法时，有时会导致意外的错误。这些错误包含模糊性，因为这两种方法都是调用的有效候选方法。编译器无法决定将方法调用绑定到哪个方法上。

```
// Java program to illustrate Varargs and ambiguity
class Test 
{
    // A method that takes varargs(here integers).
    static void fun(int ... a) 
    {
        System.out.print("fun(int ...): " +
                "Number of args: " + a.length +
                " Contents: ");

        // using for each loop to display contents of a
        for(int x : a)
            System.out.print(x + " ");

        System.out.println();
    }

    // A method that takes varargs(here booleans).
    static void fun(boolean ... a)
    {
        System.out.print("fun(boolean ...) " +
                "Number of args: " + a.length +
                " Contents: ");

        // using for each loop to display contents of a
        for(boolean x : a)
            System.out.print(x + " ");

        System.out.println();
    }

    public static void main(String args[])
    {
        // Calling overloaded fun() with different  parameter
        fun(1, 2, 3); //OK
        fun(true, false, false); //OK
        fun(); // Error: Ambiguous!
    }
}
```

在上面的程序中，fun()的重载是完全正确的。但是，由于以下调用，此程序不会编译:

```
fun(); // Error: Ambiguous!

```

根据(JLS [15.2.2](http://docs.oracle.com/javase/specs/jls/se8/html/jls-15.html#jls-15.12.2) ，重载解析有 3 个阶段:第一阶段执行重载解析，不允许装箱或取消装箱转换，第二阶段执行重载解析，同时允许装箱和取消装箱，第三阶段允许重载与变量 arity 方法、装箱和取消装箱相结合。如果在这些阶段没有找到适用的方法，那么就会出现歧义。
上面的调用可以翻译成对 fun(int …)或 fun(boolean …)的调用。两者同样有效，并且不会在重载解析的所有三个阶段后被解析，因为两种数据类型都不同。因此，这个称呼本身就是模棱两可的。

**歧义的另一个例子:**
以下 fun()的重载版本本来就有歧义:

```
static void fun(int ... a) { // method body  }
static void fun(int n, int ... a) { //method body }

```

这里，虽然 fun()的参数列表不同，但是编译器无法解析以下调用:

```
fun(1)

```

这个调用可能解析为 fun(int … a)或 fun(int n，int … a)方法，从而产生歧义。为了解决像上面这样的歧义错误，我们需要放弃重载，简单地使用两个不同的方法名。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。